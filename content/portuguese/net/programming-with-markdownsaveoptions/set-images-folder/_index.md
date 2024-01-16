---
title: Definir pasta de imagens
linktitle: Definir pasta de imagens
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir a pasta de imagens ao exportar para Markdown com Aspose.Words for .NET. Personalize o posicionamento das imagens para melhor organização e integração.
type: docs
weight: 10
url: /pt/net/programming-with-markdownsaveoptions/set-images-folder/
---

Aqui está um guia passo a passo para explicar o seguinte código-fonte C# que ajuda a definir a pasta de imagens para opções de exportação Markdown usando a biblioteca Aspose.Words para .NET. Certifique-se de incluir a biblioteca Aspose.Words em seu projeto antes de usar este código.

## Etapa 1: definir o caminho do diretório do documento

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Certifique-se de especificar o caminho correto para o diretório de documentos onde o documento que contém as imagens está localizado.

## Passo 2: Carregue o documento contendo as imagens

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Carregamos o documento especificado que contém as imagens que queremos exportar com opções de Markdown.

## Etapa 3: definir a pasta de imagens para opções de exportação de Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Criamos uma instância de`MarkdownSaveOptions` e defina o caminho para a pasta de imagens usando o`ImagesFolder` propriedade. Certifique-se de especificar o caminho correto para a pasta onde deseja salvar as imagens exportadas.

## Etapa 4: salve o documento com opções de exportação Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Salvamos o documento em um fluxo de memória usando as opções de exportação Markdown especificadas. Você pode então usar o fluxo para realizar outras operações, como salvar o conteúdo do Markdown em um arquivo.

### Exemplo de código-fonte para definir a pasta de imagens para MarkdownSaveOptions com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Este código-fonte demonstra como carregar um documento que contém imagens e, em seguida, definir a pasta de imagens para opções de exportação do Markdown. Usando as opções especificadas, o documento é salvo em um fluxo de memória. Isso permite que você personalize a localização da pasta de imagens ao exportar conteúdo Markdown.