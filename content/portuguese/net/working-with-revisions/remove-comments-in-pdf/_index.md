---
title: Remover comentários em arquivo PDF
linktitle: Remover comentários em arquivo PDF
second_title: API de processamento de documentos Aspose.Words
description: Remova comentários em um arquivo PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/remove-comments-in-pdf/
---

Neste guia passo a passo, mostraremos como remover comentários em um arquivo PDF usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Carregando o documento

primeiro passo é carregar o documento que contém os comentários.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Passo 2: Ocultar comentários em PDF

Iremos configurar a opção de layout para ocultar comentários ao gerar o PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Etapa 3: salve o documento como PDF

Por fim, salvaremos o documento em formato PDF excluindo os comentários.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Formatos de saída Markdown

A saída pode ser formatada em markdown para melhorar a legibilidade. Por exemplo :

```markdown
- Comments are hidden in the generated PDF.
```

### Exemplo de código-fonte para remover comentários em PDF usando Aspose.Words for .NET

Aqui está o código-fonte completo para remover comentários em um arquivo PDF usando Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Ocultar comentários no PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Conclusão

Neste tutorial, aprendemos como remover comentários de um arquivo PDF usando Aspose.Words for .NET. Utilizando as opções de layout adequadas, conseguimos ocultar os comentários ao gerar o PDF. Aspose.Words for .NET oferece grande flexibilidade para manipular arquivos Word e convertê-los para diferentes formatos, incluindo PDF. Agora você pode aplicar esse conhecimento para remover comentários em seus próprios arquivos PDF usando Aspose.Words for .NET.

### Perguntas frequentes para remover comentários em arquivo PDF

#### P: Como fazer upload de um documento no Aspose.Words for .NET?

 R: Use o`Document` classe de Aspose.Words for .NET para carregar um documento de um arquivo. Você pode especificar o caminho completo do documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Como ocultar comentários em PDF gerados com Aspose.Words for .NET?

 R: Use o`CommentDisplayMode` propriedade do`LayoutOptions` objeto para configurar como os comentários são exibidos ao gerar o PDF. Para ocultar comentários, defina esta propriedade como`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### P: Como salvar um documento como PDF com Aspose.Words for .NET?

 R: Use o`Save` método do`Document` objeto para salvar o documento em formato PDF. Especifique o caminho completo do arquivo PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```