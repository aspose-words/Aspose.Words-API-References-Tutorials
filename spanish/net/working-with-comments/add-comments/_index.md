---
title: Añadir comentarios
linktitle: Añadir comentarios
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a agregar comentarios a documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-comments/add-comments/
---

En este completo tutorial, aprenderá a agregar comentarios a un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá insertar comentarios y personalizar su contenido en sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: agregar contenido al documento
A continuación, agregue el contenido deseado al documento utilizando el objeto DocumentBuilder. En este ejemplo, agregamos algo de texto:

```csharp
builder.Write("Some text is added.");
```

## Paso 3: crea un comentario y agrega contenido
Para agregar un comentario, cree una instancia de la clase Comment, pasando el objeto Document, el nombre del autor, las iniciales del autor y la fecha actual:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

A continuación, agregue el comentario al párrafo actual:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Agregue contenido al comentario, como un párrafo y texto:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Paso 4: Guarde el documento
Después de agregar el comentario y su contenido, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Ejemplo de código fuente para agregar comentarios usando Aspose.Words para .NET
Aquí está el código fuente completo para agregar comentarios usando Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo agregar comentarios a un documento de Word utilizando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente provisto, ahora puede insertar comentarios y personalizar su contenido en sus documentos.

Los comentarios son útiles para colaborar, proporcionar información adicional o tomar notas dentro de un documento. Experimente con diferentes nombres de autores, iniciales y contenidos de comentarios para cumplir con sus requisitos específicos.

### Preguntas frecuentes

#### P: ¿Cómo puedo agregar un comentario en un documento de Aspose.Words para .NET?

R: Para agregar un comentario en un documento de Aspose.Words para .NET, debe seguir los pasos mencionados en el tutorial.

#### P: ¿Puedo dar formato al texto de los comentarios en Aspose.Words para .NET?

R: Sí, puede dar formato al texto de los comentarios en Aspose.Words para .NET utilizando las propiedades de formato disponibles.

#### P: ¿Cómo puedo recuperar todos los comentarios presentes en un documento?

 R: Puede recuperar todos los comentarios presentes en un documento usando el`Document.Comments` propiedad.

#### P: ¿Puedo eliminar un comentario específico en Aspose.Words para .NET?

 R: Sí, puede eliminar un comentario específico en Aspose.Words para .NET usando el`Comment.Remove` método.

#### P: ¿Cómo puedo modificar el texto de un comentario existente en Aspose.Words para .NET?

 R: Para modificar el texto de un comentario existente en Aspose.Words for .NET, puede acceder a la`Comment.Text` propiedad de la correspondiente`Comment` objeto y modifique el texto según sea necesario.