---
title: Obtenha substituição sem sufixos
linktitle: Obtenha substituição sem sufixos
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como gerenciar a substituição de fontes sem sufixos em Aspose.Words for .NET. Siga nosso guia passo a passo para garantir que seus documentos tenham sempre uma aparência perfeita.
type: docs
weight: 10
url: /pt/net/working-with-fonts/get-substitution-without-suffixes/
---

Bem-vindo a este guia completo sobre como gerenciar a substituição de fontes usando Aspose.Words for .NET. Se você já teve problemas com fontes que não apareciam corretamente em seus documentos, você veio ao lugar certo. Este tutorial o guiará por um processo passo a passo para lidar com a substituição de fontes sem sufixos de maneira eficiente. Vamos começar!

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter o seguinte:

- Conhecimento básico de C#: Compreender a programação C# tornará mais fácil seguir e implementar as etapas.
-  Biblioteca Aspose.Words for .NET: Baixe e instale a biblioteca do[Link para Download](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: configure um ambiente de desenvolvimento como o Visual Studio para escrever e executar seu código.
-  Documento de amostra: Um documento de amostra (por exemplo,`Rendering.docx`) para trabalhar durante este tutorial.

## Importar namespaces

Primeiro, precisamos importar os namespaces necessários para acessar as classes e métodos fornecidos pelo Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## Etapa 1: definir o diretório de documentos

Para começar, especifique o diretório onde seu documento está localizado. Isso ajuda a localizar o documento no qual você deseja trabalhar.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: configurar o manipulador de aviso de substituição

Em seguida, precisamos configurar um manipulador de aviso que nos notificará sempre que ocorrer uma substituição de fonte durante o processamento do documento. Isso é crucial para detectar e lidar com quaisquer problemas de fonte.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Etapa 3: adicionar fontes de fontes personalizadas

Nesta etapa, adicionaremos fontes de fontes personalizadas para garantir que Aspose.Words possa localizar e usar as fontes corretas. Isto é particularmente útil se você tiver fontes específicas armazenadas em diretórios personalizados.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

Neste código:
-  Recuperamos as fontes de fontes atuais e adicionamos uma nova`FolderFontSource` apontando para nosso diretório de fontes personalizadas (`C:\\MyFonts\\`).
- Em seguida, atualizamos as fontes de fontes com esta nova lista.

## Etapa 4: salve o documento

Por fim, salve o documento após aplicar as configurações de substituição de fonte. Para este tutorial, vamos salvá-lo como PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Etapa 5: Crie a classe do manipulador de avisos

Para lidar com avisos de forma eficaz, crie uma classe personalizada que implemente o`IWarningCallback` interface. Esta classe irá capturar e registrar quaisquer avisos de substituição de fonte.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

Nesta aula:
-  O`Warning` O método captura avisos relacionados à substituição de fontes.
-  O`FontWarnings` A coleção armazena esses avisos para inspeção ou registro adicional.

## Conclusão

Agora você dominou o processo de manipulação de substituição de fontes sem sufixos usando Aspose.Words for .NET. Esse conhecimento garantirá que seus documentos mantenham a aparência pretendida, independentemente das fontes disponíveis no sistema. Continue experimentando diferentes configurações e fontes para aproveitar totalmente o poder do Aspose.Words.

## Perguntas frequentes

### P1: Como posso usar fontes de vários diretórios personalizados?

 Você pode adicionar vários`FolderFontSource` instâncias para o`fontSources` liste e atualize as fontes de fonte de acordo.

### Q2: Onde posso baixar uma avaliação gratuita do Aspose.Words for .NET?

 Você pode baixar uma versão de teste gratuita no site[Aspose página de teste gratuito](https://releases.aspose.com/).

###  Q3: Posso lidar com vários tipos de avisos usando`IWarningCallback`?

 Sim o`IWarningCallback` interface permite lidar com vários tipos de avisos, não apenas com a substituição de fontes.

### Q4: Onde posso obter suporte para Aspose.Words?

 Para suporte, visite o[Fórum de suporte Aspose.Words](https://forum.aspose.com/c/words/8).

### P5: É possível adquirir uma licença temporária?

 Sim, você pode obter uma licença temporária do[página de licença temporária](https://purchase.aspose.com/temporary-license/).