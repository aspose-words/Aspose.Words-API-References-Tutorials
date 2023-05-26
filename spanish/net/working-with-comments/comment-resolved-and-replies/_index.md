---
title: Comentario resuelto y respuestas
linktitle: Comentario resuelto y respuestas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a resolver comentarios y sus respuestas en documentos de Word utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-comments/comment-resolved-and-replies/
---

En este completo tutorial, aprenderá a resolver comentarios y sus respuestas en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá administrar la resolución de comentarios y actualizar el estado de los comentarios y sus respuestas.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cargue el documento y acceda a los comentarios
Para comenzar, cargue el documento que contiene los comentarios usando la clase Document y acceda a la colección de comentarios:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Paso 2: resuelve los comentarios y sus respuestas
A continuación, repita los comentarios y sus respuestas para marcarlos como resueltos:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

En el código anterior, accedemos al comentario principal e iteramos a través de sus respuestas. Podemos recuperar el ID del comentario principal y su estado de resolución. Luego, actualizamos la marca "Terminado" de cada respuesta de comentario para indicar la resolución.

## Paso 3: Guarde el documento
Después de resolver los comentarios y actualizar su estado, guarde el documento modificado en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Código fuente de ejemplo para resolver comentarios y sus respuestas usando Aspose.Words para .NET
Aquí está el código fuente completo para resolver comentarios y sus respuestas usando Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Recuerde ajustar el código de acuerdo con sus requisitos específicos, incluida la ruta del archivo del documento y la personalización adicional.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo resolver comentarios y sus respuestas en un documento de Word utilizando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente provisto, ahora puede administrar la resolución de comentarios y actualizar el estado de los comentarios y sus respuestas de acuerdo con sus requisitos.

La resolución de comentarios ayuda a rastrear y administrar los comentarios dentro de un documento. Experimente con diferentes estados de comentarios y personalícelos para mejorar los procesos de colaboración y revisión en sus documentos.
