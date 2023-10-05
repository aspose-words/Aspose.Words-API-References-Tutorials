---
title: Aceptar revisiones
linktitle: Aceptar revisiones
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo aceptar revisiones de un documento de Word usando Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/working-with-revisions/accept-revisions/
---

En este tutorial, lo guiaremos en la aceptación de revisiones de un documento de Word utilizando la función Aceptar revisiones de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aceptar cambios en el documento.

## Paso 1: Agregar y editar el contenido del documento

En este ejemplo, estamos creando un documento y agregando contenido. Usamos varios párrafos para ilustrar los cambios y revisiones. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Agregue texto al primer párrafo y luego agregue dos párrafos más.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Paso 2: realizar un seguimiento de las reseñas y agregar reseñas

Habilitamos el seguimiento de revisiones y agregamos una revisión al documento. Así es cómo:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Este párrafo es una revisión y tendrá establecida la bandera "IsInsertRevision" correspondiente.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Paso 3: eliminar un párrafo y gestionar las revisiones

Eliminamos un párrafo y comprobamos las revisiones guardadas. Así es cómo:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Como estamos realizando un seguimiento de las revisiones, el párrafo aún existe en el documento y tendrá activada la marca "IsDeleteRevision".
// y se mostrará como una reseña en Microsoft Word, hasta que aceptemos o rechacemos todas las reseñas.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Paso 4: aceptar cambios

Aceptamos todos los cambios en el documento. Así es cómo:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Paso 5: dejar de rastrear reseñas

Dejaremos de rastrear las revisiones para que los cambios en el documento ya no aparezcan como revisiones. Así es cómo:

```csharp
doc.StopTrackRevisions();
```
## Paso 6: guardar el documento

 Después de insertar el campo del formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Código fuente de ejemplo para Aceptar revisiones usando Aspose.Words para .NET

Aquí está el código fuente completo para aceptar cambios en un documento usando Aspose.Words para .NET:


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Agregue texto al primer párrafo y luego agregue dos párrafos más.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Tenemos tres párrafos, ninguno de los cuales registrado como ningún tipo de revisión.
// Si agregamos/eliminamos algún contenido en el documento mientras realizamos el seguimiento de las revisiones,
// se mostrarán como tales en el documento y podrán ser aceptados/rechazados.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Este párrafo es una revisión y tendrá establecida la bandera "IsInsertRevision" correspondiente.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Obtenga la colección de párrafos del documento y elimine un párrafo.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Dado que estamos realizando un seguimiento de las revisiones, el párrafo aún existe en el documento y tendrá la opción "IsDeleteRevision" configurada.
// y se mostrará como una revisión en Microsoft Word, hasta que aceptemos o rechacemos todas las revisiones.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// El párrafo de eliminación de revisión se elimina una vez que aceptamos los cambios.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Al detener el seguimiento de las revisiones, este texto aparece como texto normal.
// Las revisiones no se cuentan cuando se modifica el documento.
doc.StopTrackRevisions();

// Guarde el documento.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Conclusión

En este tutorial, aprendimos cómo aceptar revisiones en un documento de Word utilizando la función Aceptar revisiones de Aspose.Words para .NET. Hemos seguido los pasos para agregar y editar el contenido del documento, realizar un seguimiento de las revisiones, eliminar un párrafo revisado, aceptar todos los cambios y dejar de realizar el seguimiento de las revisiones. Ahora puede aplicar este conocimiento para gestionar eficazmente las revisiones de sus propios documentos de Word utilizando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo habilito el seguimiento de revisiones en Aspose.Words para .NET?

#### Solución 1:

 R: Para habilitar el seguimiento de revisiones en Aspose.Words para .NET, utilice el`StartTrackRevisions` método de la`Document` objeto y especifique el nombre del autor y la fecha de inicio para el seguimiento de la revisión.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Solución 2:

 R: También puede habilitar el seguimiento de revisiones usando el`Document` constructor que acepta`trackRevisions` y`author` parámetros.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### P: ¿Cómo aceptar todos los cambios en un documento con Aspose.Words para .NET?

 R: Utilice el`AcceptAllRevisions` método de la`Document` oponerse a aceptar todos los cambios realizados en el documento.

```csharp
doc.AcceptAllRevisions();
```

#### P: ¿Cómo guardo un documento modificado con revisiones aceptadas?

 Utilizar el`Save` método de la`Document` objeto para guardar el documento modificado con las revisiones aceptadas. Asegúrese de proporcionar la ruta del archivo correcta.

```csharp
doc.Save("path/to/the/document.docx");
```

#### P: ¿Cómo dejo de realizar el seguimiento de las revisiones en Aspose.Words para .NET?

 R: Utilice el`StopTrackRevisions` método de la`Document` objeto para detener las revisiones de seguimiento.

```csharp
doc.StopTrackRevisions();
```

#### P: ¿Cómo elimino un párrafo revisado en un documento con Aspose.Words para .NET?

 R: Para eliminar un párrafo revisado en un documento, puede utilizar el`Remove` Método de recopilación de párrafos.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```