---
title: Detectar formato de arquivo de documento
linktitle: Detectar formato de arquivo de documento
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como detectar formatos de arquivo de documentos usando Aspose.Words for .NET com este guia passo a passo abrangente.
type: docs
weight: 10
url: /pt/net/programming-with-fileformat/detect-file-format/
---
## Introdução

No mundo digital de hoje, a gestão eficiente de diferentes formatos de documentos é crucial. Esteja você lidando com Word, PDF, HTML ou outros formatos, ser capaz de detectar e processar esses arquivos corretamente pode economizar muito tempo e esforço. Neste tutorial, exploraremos como detectar formatos de arquivo de documentos usando Aspose.Words for .NET. Este guia orientará você em tudo o que você precisa saber, desde os pré-requisitos até um guia passo a passo detalhado.

## Pré-requisitos

Antes de mergulharmos no código, vamos ter certeza de que você tem tudo o que precisa:

-  Aspose.Words for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/) . Certifique-se de ter uma licença válida. Se não, você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/).
- Visual Studio: qualquer versão recente funcionará bem.
- .NET Framework: certifique-se de ter a versão correta instalada.

## Importar namespaces

Para começar, você precisará importar os namespaces necessários para o seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

Vamos dividir o exemplo em várias etapas para facilitar o acompanhamento.

## Etapa 1: configurar diretórios

Primeiro, precisamos configurar diretórios onde os arquivos serão classificados com base em seu formato.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Crie os diretórios se eles ainda não existirem.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## Etapa 2: obtenha a lista de arquivos

A seguir, obteremos uma lista de arquivos do diretório, excluindo quaisquer documentos corrompidos.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Etapa 3: detectar formatos de arquivo

Agora, iteramos cada arquivo e detectamos seu formato usando Aspose.Words.

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // Exibir o tipo de documento
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## Conclusão

Detectar formatos de arquivo de documentos usando Aspose.Words for .NET é um processo simples. Ao configurar seus diretórios, obter sua lista de arquivos e utilizar Aspose.Words para detectar formatos de arquivo, você pode organizar e gerenciar seus documentos com eficiência. Essa abordagem não apenas economiza tempo, mas também garante que você lide corretamente com vários formatos de documentos.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para trabalhar programaticamente com documentos do Word. Ele permite que os desenvolvedores criem, modifiquem e convertam documentos em vários formatos.

### O Aspose.Words pode detectar documentos criptografados?
Sim, o Aspose.Words pode detectar se um documento está criptografado e você pode lidar com esses documentos de acordo.

### Quais formatos o Aspose.Words pode detectar?
Aspose.Words pode detectar uma ampla variedade de formatos, incluindo DOC, DOCX, RTF, HTML, MHTML, ODT e muitos mais.

### Como posso obter uma licença temporária do Aspose.Words?
 Você pode obter uma licença temporária do[Assuma a compra](https://purchase.aspose.com/temporary-license/) página.

### Onde posso encontrar a documentação do Aspose.Words?
 A documentação do Aspose.Words pode ser encontrada[aqui](https://reference.aspose.com/words/net/).
