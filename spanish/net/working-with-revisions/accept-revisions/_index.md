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

// Agregue texto al primer párrafo, luego agregue dos párrafos más.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Paso 2: Haga un seguimiento de las reseñas y agregue reseñas

Habilitamos el seguimiento de revisión y agregamos una revisión al documento. Así es cómo:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//Este párrafo es una revisión y tendrá el indicador "IsInsertRevision" correspondiente establecido.
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

// Agregue texto al primer párrafo, luego agregue dos párrafos más.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Tenemos tres párrafos, ninguno de los cuales registrado como ningún tipo de revisión
//Si agregamos/eliminamos cualquier contenido en el documento durante el seguimiento de las revisiones,
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
// Las revisiones no se cuentan cuando se cambia el documento.
doc.StopTrackRevisions();

// Guarde el documento.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
