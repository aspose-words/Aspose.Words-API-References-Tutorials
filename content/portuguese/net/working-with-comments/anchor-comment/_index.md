---
title: Comentário âncora
linktitle: Comentário âncora
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ancorar respostas de comentários a textos específicos em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-comments/anchor-comment/
---

Neste tutorial abrangente, você aprenderá como ancorar respostas de comentários a um texto específico em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá associar comentários a textos específicos em seus documentos.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: crie um novo documento e adicione texto
Para começar, crie um novo documento usando a classe Document e adicione o texto desejado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Etapa 2: crie um comentário e adicione um intervalo de comentários
seguir, crie um comentário e associe-o a um texto específico usando os objetos CommentRangeStart e CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Etapa 3: salve o documento
Após ancorar o comentário em um texto específico, salve o documento em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Exemplo de código-fonte para resposta de comentário âncora usando Aspose.Words para .NET
Aqui está o código-fonte completo para ancorar uma resposta de comentário usando Aspose.Words for .NET:

```csharp
// Crie uma instância do Documento.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Crie três objetos Run.
// Os dois primeiros executam algum texto, enquanto o terceiro executa um comentário

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Cada um dos objetos Run possui um objeto CommentRangeStart e CommentRangeEnd associado.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Perguntas frequentes

#### P: O que é uma âncora de comentário no Aspose.Words for .NET?

R: No Aspose.Words for .NET, uma âncora de comentário é um marcador que conecta um comentário a um local específico em um documento.

#### P: Como posso adicionar uma âncora de comentário em um documento Aspose.Words for .NET?

R: Para adicionar uma âncora de comentário em um documento Aspose.Words for .NET, siga as etapas mencionadas no tutorial.

#### P: Como faço para acessar uma âncora de comentário existente no Aspose.Words for .NET?

 R: Você pode acessar uma âncora de comentário existente no Aspose.Words for .NET usando o`Comment.Anchor` propriedade.

#### P: Posso suprimir uma âncora de comentário no Aspose.Words for .NET?

 R: Sim, você pode remover uma âncora de comentário no Aspose.Words for .NET usando o`Comment.Remove` método.

#### P: Como posso editar o texto de um comentário vinculado a uma âncora de comentário no Aspose.Words for .NET?

 R: Para modificar o texto de um comentário vinculado a uma âncora de comentário no Aspose.Words for .NET, você pode acessar o`Comment.Text` propriedade do correspondente`Comment` objeto e modifique o texto conforme necessário.

