---
title: Aceptar revisiones
linktitle: Aceptar revisiones
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a aceptar revisiones de un documento de Word usando Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/working-with-revisions/accept-revisions/
---

En este tutorial, lo guiaremos a través de la aceptación de revisiones de un documento de Word utilizando la función Aceptar revisiones de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aceptar los cambios en el documento.

## Paso 1: agregar y editar el contenido del documento

En este ejemplo, estamos creando un documento y agregando contenido. Usamos varios párrafos para ilustrar cambios y revisiones. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Agregue texto al primer párrafo, luego agregue dos párrafos más.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Paso 2: Haga un seguimiento de las reseñas y agregue reseñas

Habilitamos el seguimiento de revisión y agregamos una revisión al documento. Así es cómo:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Este párrafo es una revisión y tendrá el indicador "IsInsertRevision" correspondiente establecido.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Paso 3: Elimina un párrafo y administra las revisiones

Eliminamos un párrafo y verificamos las revisiones guardadas. Así es cómo:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Como estamos rastreando las revisiones, el párrafo aún existe en el documento, tendrá el indicador "IsDeleteRevision" establecido
// y se mostrará como una revisión en Microsoft Word, hasta que aceptemos o rechacemos todas las revisiones.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Paso 4: Aceptar cambios

Aceptamos todos los cambios en el documento. Así es cómo:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Paso 5: Deja de rastrear las reseñas

Vamos a dejar de rastrear las revisiones para que los cambios en el documento ya no se muestren como revisiones. Así es cómo:

```csharp
doc.StopTrackRevisions();
```
## Paso 6: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Ejemplo de código fuente para Aceptar revisiones usando Aspose.Words para .NET

Aquí está el código fuente completo para aceptar cambios en un documento usando Aspose.Words para .NET:


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Agregue texto al primer párrafo, luego agregue dos párrafos más.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Tenemos tres párrafos, ninguno de los cuales registrado como ningún tipo de revisión
// Si agregamos/eliminamos cualquier contenido en el documento durante el seguimiento de las revisiones,
// se mostrarán como tales en el documento y se pueden aceptar/rechazar.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Este párrafo es una revisión y tendrá el indicador correspondiente "IsInsertRevision" establecido.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Obtenga la colección de párrafos del documento y elimine un párrafo.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Dado que estamos rastreando las revisiones, el párrafo aún existe en el documento, tendrá el conjunto "IsDeleteRevision"
// y se mostrará como una revisión en Microsoft Word, hasta que aceptemos o rechacemos todas las revisiones.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// El párrafo de eliminación de revisión se elimina una vez que aceptamos los cambios.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Detener el seguimiento de las revisiones hace que este texto aparezca como texto normal.
//Las revisiones no se cuentan cuando se cambia el documento.
doc.StopTrackRevisions();

// Guarde el documento.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Conclusión

En este tutorial, aprendimos cómo aceptar revisiones en un documento de Word utilizando la función Aceptar revisiones de Aspose.Words para .NET. Hemos seguido los pasos para agregar y editar el contenido del documento, realizar un seguimiento de las revisiones, eliminar un párrafo revisado, aceptar todos los cambios y detener el seguimiento de las revisiones. Ahora puede aplicar este conocimiento para administrar de manera efectiva las revisiones en sus propios documentos de Word usando Aspose.Words para .NET.

### preguntas frecuentes

#### P: ¿Cómo habilito el seguimiento de revisiones en Aspose.Words para .NET?

#### Solución 1:

 R: Para habilitar el seguimiento de revisión en Aspose.Words para .NET, use el`StartTrackRevisions` metodo de la`Document` objeto y especifique el nombre del autor y la fecha de inicio para el seguimiento de revisiones.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Solución 2:

 R: También puede habilitar el seguimiento de revisión usando el`Document` constructor que acepta`trackRevisions` y`author` parámetros

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### P: ¿Cómo aceptar todos los cambios en un documento con Aspose.Words para .NET?

 R: Usa el`AcceptAllRevisions` metodo de la`Document` oponerse a aceptar todos los cambios realizados en el documento.

```csharp
doc.AcceptAllRevisions();
```

#### P: ¿Cómo guardo un documento modificado con revisiones aceptadas?

 Utilizar el`Save` metodo de la`Document` objeto para guardar el documento modificado con las revisiones aceptadas. Asegúrese de proporcionar la ruta de archivo correcta.

```csharp
doc.Save("path/to/the/document.docx");
```

#### P: ¿Cómo dejo de realizar un seguimiento de las revisiones en Aspose.Words para .NET?

 R: Usa el`StopTrackRevisions` metodo de la`Document` objeto para detener las revisiones de seguimiento.

```csharp
doc.StopTrackRevisions();
```

#### P: ¿Cómo elimino un párrafo revisado en un documento con Aspose.Words para .NET?

 R: Para eliminar un párrafo revisado en un documento, puede usar el`Remove` método de la colección de párrafos.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```