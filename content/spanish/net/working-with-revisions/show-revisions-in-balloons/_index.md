---
title: Mostrar revisiones en globos
linktitle: Mostrar revisiones en globos
second_title: API de procesamiento de documentos de Aspose.Words
description: Muestre revisiones en globos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/show-revisions-in-balloons/
---

En esta guía paso a paso, le mostraremos cómo mostrar revisiones en globos en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Cargar el documento

El primer paso es cargar el documento que contiene las revisiones.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: Configure las opciones de visualización de reseñas

Configuraremos las opciones de mostrar para que las revisiones sean visibles en globos.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Paso 3: Guarda el documento en formato PDF

Finalmente, guardaremos el documento como PDF con las revisiones mostradas en globos.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Formatos de salida de rebajas

La salida se puede formatear en Markdown para mejorar la legibilidad. Por ejemplo :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Ejemplo de código fuente para Mostrar revisiones en globos usando Aspose.Words para .NET

Aquí está el código fuente completo para mostrar las revisiones en globos en un documento usando Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Renderiza revisiones de inserción en línea, elimina y formatea revisiones en globos.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Representa barras de revisión en el lado derecho de una página.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Conclusión

En este tutorial, aprendimos a mostrar revisiones en globos en un documento de Word usando Aspose.Words para .NET. Al usar las opciones de visualización adecuadas, pudimos hacer que las revisiones fueran visibles en burbujas con barras de revisión en el lado derecho. Aspose.Words para .NET ofrece muchas funciones potentes para manipular documentos de Word, incluida la gestión de revisiones. Ahora puede usar este conocimiento para mostrar revisiones en globos en sus propios documentos de Word usando Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo cargar un documento en Aspose.Words para .NET?

 R: Usa el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo mostrar revisiones en globos con Aspose.Words para .NET?

 R: Usa el`ShowInBalloons` propiedad de la`RevisionOptions` objeto para configurar la visualización de revisiones en globos. Puede establecer esta propiedad en`ShowInBalloons.FormatAndDelete` para mostrar revisiones en globos con borrado y revisiones de formato.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### P: ¿Cómo guardar un documento en formato PDF con Aspose.Words para .NET?

 R: Usa el`Save` metodo de la`Document` objeto para guardar el documento en formato PDF. Debe especificar la ruta de destino completa con la extensión ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```