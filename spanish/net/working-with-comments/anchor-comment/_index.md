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
A continuación, cree un comentario y asócielo con un texto específico utilizando los objetos CommentRangeStart y CommentRangeEnd:

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
// Cree una instancia del documento.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Cree tres objetos Ejecutar.
//Los dos primeros ejecutan un texto, mientras que el tercero ejecuta un comentario

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

// Cada uno de los objetos Run tiene un objeto CommentRangeStart y CommentRangeEnd asociado.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Preguntas frecuentes

#### P: ¿Qué es un ancla de comentario en Aspose.Words para .NET?

R: En Aspose.Words para .NET, un ancla de comentario es un marcador que conecta un comentario con una ubicación específica en un documento.

#### P: ¿Cómo puedo agregar un ancla de comentario en un documento de Aspose.Words para .NET?

R: Para agregar un ancla de comentario en un documento de Aspose.Words para .NET, siga los pasos mencionados en el tutorial.

#### P: ¿Cómo accedo a un ancla de comentario existente en Aspose.Words para .NET?

 R: Puede acceder a un ancla de comentario existente en Aspose.Words para .NET usando el`Comment.Anchor` propiedad.

#### P: ¿Puedo suprimir un ancla de comentario en Aspose.Words para .NET?

 R: Sí, puede eliminar un ancla de comentario en Aspose.Words para .NET usando el`Comment.Remove` método.

#### P: ¿Cómo puedo editar el texto de un comentario vinculado a un ancla de comentario en Aspose.Words para .NET?

R: Para modificar el texto de un comentario vinculado a un ancla de comentario en Aspose.Words para .NET, puede acceder a la`Comment.Text` propiedad de la correspondiente`Comment` objeto y modifique el texto según sea necesario.

