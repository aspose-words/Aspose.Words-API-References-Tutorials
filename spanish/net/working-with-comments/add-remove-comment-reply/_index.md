---
title: Añadir Quitar Comentar Responder
linktitle: Añadir Quitar Comentar Responder
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a agregar y eliminar respuestas de comentarios en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-comments/add-remove-comment-reply/
---

En este completo tutorial, aprenderá a agregar y eliminar respuestas de comentarios en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá administrar las respuestas a los comentarios y personalizarlas de acuerdo con sus requisitos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cargue el Documento
Para empezar, carga el documento que contiene los comentarios usando la clase Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Paso 2: acceda al comentario y administre las respuestas
A continuación, acceda al comentario del documento mediante el método GetChild con el parámetro NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Para eliminar una respuesta del comentario, use el método RemoveReply y proporcione el índice de respuesta deseado:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Para agregar una nueva respuesta al comentario, use el método AddReply y proporcione el nombre del autor, las iniciales del autor, la fecha y la hora y el texto de la respuesta:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Paso 3: Guarde el documento
Después de agregar o eliminar las respuestas a los comentarios, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Ejemplo de código fuente para agregar y eliminar respuestas de comentarios usando Aspose.Words para .NET
Aquí está el código fuente completo para agregar y eliminar respuestas de comentarios usando Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo agregar y eliminar respuestas de comentarios en un documento de Word usando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente provisto, ahora puede administrar las respuestas a los comentarios y personalizarlas según sus requisitos.

Las respuestas a comentarios permiten debates colaborativos y comentarios dentro de un documento. Experimente con diferentes autores de respuestas, iniciales, fechas y textos para mejorar la colaboración y la comunicación dentro de sus documentos.

### Preguntas frecuentes

#### P: ¿Cómo puedo agregar un comentario en Aspose.Words para .NET?

 R: Para agregar un comentario en Aspose.Words para .NET, puede usar el`Comment.AddComment` método que especifica el texto del comentario y dónde desea agregarlo en el documento.

#### P: ¿Cómo puedo eliminar un comentario en Aspose.Words para .NET?

 R: Para eliminar un comentario en Aspose.Words para .NET, puede usar el`Comment.Remove` método que especifica el`Comment` objeto que desea eliminar.

#### P: ¿Puedo responder a un comentario en Aspose.Words para .NET?

 R: Sí, puede responder a un comentario en Aspose.Words para .NET usando el`Comment.AddReply` método especificando el texto de respuesta y dónde desea agregarlo en el documento.

#### P: ¿Cómo puedo acceder a los comentarios existentes en Aspose.Words para .NET?

 R: Puede acceder a los comentarios existentes en Aspose.Words para .NET usando el`CommentCollection`propiedad de la`Document`objeto. Esto le permitirá navegar por todos los comentarios presentes en el documento.

#### P: ¿Puedo editar el texto de un comentario en Aspose.Words para .NET?

 R: Sí, puede editar el texto de un comentario en Aspose.Words for .NET accediendo a la`Comment.Text` propiedad de la correspondiente`Comment` objeto y modificando el texto según sea necesario.