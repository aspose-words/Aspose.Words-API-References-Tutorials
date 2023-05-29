---
title: Comentario ancla
linktitle: Comentario ancla
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a anclar respuestas de comentarios a texto específico en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-comments/anchor-comment/
---

En este completo tutorial, aprenderá a anclar las respuestas de los comentarios a un texto específico en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá asociar comentarios con texto específico en sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: cree un nuevo documento y agregue texto
Para comenzar, cree un nuevo documento usando la clase Documento y agregue el texto deseado:

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

## Paso 2: cree un comentario y agregue un rango de comentarios
A continuación, cree un comentario y asócielo con un texto específico usando los objetos CommentRangeStart y CommentRangeEnd:

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

## Paso 3: Guarde el documento
Después de anclar el comentario a un texto específico, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Ejemplo de código fuente para la respuesta de comentario de anclaje usando Aspose.Words para .NET
Aquí está el código fuente completo para anclar una respuesta de comentario usando Aspose.Words para .NET:

```csharp
// Create an instance of the Document.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Create three Run objects.
// The first two run some text, while the third runs a Comment

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

// Each of the Run objects has an associated CommentRangeStart and CommentRangeEnd object.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```
