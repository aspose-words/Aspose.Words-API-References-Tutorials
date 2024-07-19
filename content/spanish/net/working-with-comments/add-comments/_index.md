---
title: Añadir comentarios
linktitle: Añadir comentarios
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar comentarios a documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-comments/add-comments/
---

En este completo tutorial, aprenderá cómo agregar comentarios a un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá insertar comentarios y personalizar su contenido en sus documentos.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: crear un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Documento e inicialice un objeto DocumentBuilder:

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

## Paso 3: cree un comentario y agregue contenido
Para agregar un comentario, cree una instancia de la clase Comentario, pasando el objeto Documento, el nombre del autor, las iniciales del autor y la fecha actual:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

continuación, agregue el comentario al párrafo actual:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Agregue contenidos al comentario, como un párrafo y texto:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Paso 4: guarde el documento
Después de agregar el comentario y su contenido, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Código fuente de ejemplo para agregar comentarios usando Aspose.Words para .NET
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
¡Felicidades! Ha aprendido con éxito cómo agregar comentarios a un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede insertar comentarios y personalizar su contenido en sus documentos.

Los comentarios son útiles para colaborar, proporcionar información adicional o tomar notas dentro de un documento. Experimente con diferentes nombres de autores, iniciales y contenidos de comentarios para satisfacer sus requisitos específicos.

### Preguntas frecuentes

#### P: ¿Cómo puedo agregar un comentario en un documento de Aspose.Words para .NET?

R: Para agregar un comentario en un documento de Aspose.Words para .NET, debe seguir los pasos mencionados en el tutorial.

#### P: ¿Puedo formatear el texto del comentario en Aspose.Words para .NET?

R: Sí, puede formatear el texto del comentario en Aspose.Words para .NET usando las propiedades de formato disponibles.

#### P: ¿Cómo puedo recuperar todos los comentarios presentes en un documento?

 R: Puede recuperar todos los comentarios presentes en un documento usando el`Document.Comments` propiedad.

#### P: ¿Puedo eliminar un comentario específico en Aspose.Words para .NET?

 R: Sí, puede eliminar un comentario específico en Aspose.Words para .NET usando el`Comment.Remove` método.

#### P: ¿Cómo puedo modificar el texto de un comentario existente en Aspose.Words para .NET?

 R: Para modificar el texto de un comentario existente en Aspose.Words para .NET, puede acceder al`Comment.Text` propiedad de la correspondiente`Comment` objeto y modifique el texto según sea necesario.