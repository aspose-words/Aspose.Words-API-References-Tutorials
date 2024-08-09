---
title: Insira objeto Ole no Word com pacote Ole
linktitle: Insira objeto Ole no Word com pacote Ole
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir objetos OLE em documentos do Word usando Aspose.Words for .NET. Siga nosso guia passo a passo detalhado para incorporar arquivos perfeitamente.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## Introdução

Se você sempre quis incorporar um arquivo em um documento do Word, você está no lugar certo. Quer seja um arquivo ZIP, uma planilha do Excel ou qualquer outro tipo de arquivo, incorporá-lo diretamente ao seu documento do Word pode ser extremamente útil. Pense nisso como ter um compartimento secreto em seu documento onde você pode guardar todo tipo de tesouro. E hoje vamos ver como fazer isso usando Aspose.Words for .NET. Pronto para se tornar um assistente do Word? Vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1. Aspose.Words for .NET: Se ainda não o fez, baixe-o em[aqui](https://releases.aspose.com/words/net/).
2. Um ambiente de desenvolvimento: Visual Studio ou qualquer outro ambiente de desenvolvimento .NET.
3. Compreensão básica de C#: Você não precisa ser um especialista, mas conhecer o C# ajudará.
4. Um diretório de documentos: uma pasta onde você pode armazenar e recuperar documentos.

## Importar namespaces

Primeiramente, vamos colocar nossos namespaces em ordem. Você precisa incluir os seguintes namespaces em seu projeto:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Vamos dividir isso em etapas pequenas, para que seja fácil acompanhar.

## Etapa 1: configure seu documento

Imagine que você é um artista com uma tela em branco. Primeiro, precisamos da nossa tela em branco, que é o nosso documento Word. Veja como você configura:

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Este código inicializa um novo documento do Word e configura um DocumentBuilder, que usaremos para inserir conteúdo em nosso documento.

## Etapa 2: leia seu objeto Ole

A seguir, vamos ler o arquivo que você deseja incorporar. Pense nisso como pegar o tesouro que você deseja esconder em seu compartimento secreto:

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

Esta linha lê todos os bytes do seu arquivo ZIP e os armazena em uma matriz de bytes.

## Etapa 3: insira o objeto Ole

Agora vem a parte mágica. Vamos incorporar o arquivo em nosso documento do Word:

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 Aqui, criamos um fluxo de memória a partir da matriz de bytes e usamos o`InsertOleObject` método para incorporá-lo ao documento. Também definimos o nome do arquivo e o nome de exibição do objeto incorporado.

## Etapa 4: salve seu documento

Finalmente, vamos salvar nossa obra-prima:

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Isso salva o documento com seu arquivo incorporado no diretório especificado.

## Conclusão

E aí está! Você incorporou com sucesso um objeto OLE em um documento do Word usando Aspose.Words for .NET. É como adicionar uma joia escondida dentro do seu documento que pode ser revelada a qualquer momento. Essa técnica pode ser extremamente útil para diversas aplicações, desde documentação técnica até relatórios dinâmicos. 

## Perguntas frequentes

### Posso incorporar outros tipos de arquivo usando este método?
Sim, você pode incorporar vários tipos de arquivos, como planilhas Excel, PDFs e imagens.

### Preciso de uma licença para Aspose.Words?
 Sim, você precisa de uma licença válida. Você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/) para avaliação.

### Como posso personalizar o nome de exibição do objeto OLE?
 Você pode definir o`DisplayName` propriedade do`OlePackage` para personalizá-lo.

### O Aspose.Words é compatível com o .NET Core?
Sim, Aspose.Words oferece suporte a .NET Framework e .NET Core.

### Posso editar o objeto OLE incorporado no documento do Word?
Não, você não pode editar o objeto OLE diretamente no Word. Você precisa abri-lo em seu aplicativo nativo.