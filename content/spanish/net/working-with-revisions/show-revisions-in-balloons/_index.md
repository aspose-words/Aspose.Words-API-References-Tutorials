---
title: Mostrar revisiones en globos
linktitle: Mostrar revisiones en globos
second_title: API de procesamiento de documentos Aspose.Words
description: Mostrar revisiones en globos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/show-revisions-in-balloons/
---

En esta guía paso a paso, le mostraremos cómo mostrar revisiones en globos en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de rebajas.

## Paso 1: cargar el documento

El primer paso es subir el documento que contiene las revisiones.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: configurar las opciones de presentación de reseñas

Configuraremos las opciones de mostrar para que las revisiones sean visibles en globos.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Paso 3: guarde el documento en formato PDF

Finalmente, guardaremos el documento como PDF con las revisiones mostradas en globos.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Formatos de salida de rebajas

La salida se puede formatear en rebajas para mejorar la legibilidad. Por ejemplo :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Código fuente de ejemplo para Mostrar revisiones en globos usando Aspose.Words para .NET

Aquí está el código fuente completo para mostrar revisiones en globos en un documento usando Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Procesa insertar revisiones en línea, eliminar y formatear revisiones en globos.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Representa barras de revisión en el lado derecho de una página.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Conclusión

En este tutorial, aprendimos cómo mostrar revisiones en globos en un documento de Word usando Aspose.Words para .NET. Al utilizar las opciones de visualización adecuadas, pudimos hacer que las revisiones fueran visibles en burbujas con barras de revisión en el lado derecho. Aspose.Words para .NET ofrece muchas funciones potentes para manipular documentos de Word, incluida la gestión de revisiones. Ahora puede utilizar este conocimiento para mostrar revisiones en globos en sus propios documentos de Word usando Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo cargar un documento en Aspose.Words para .NET?

 R: Utilice el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo mostrar revisiones en globos con Aspose.Words para .NET?

 R: Utilice el`ShowInBalloons` propiedad de la`RevisionOptions` objeto para configurar la visualización de revisiones en globos. Puede establecer esta propiedad en`ShowInBalloons.FormatAndDelete` para mostrar revisiones en globos con revisiones de eliminación y formato.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### P: ¿Cómo guardar un documento en formato PDF con Aspose.Words para .NET?

 R: Utilice el`Save` método de la`Document` objeto para guardar el documento en formato PDF. Debe especificar la ruta de destino completa con la extensión ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```