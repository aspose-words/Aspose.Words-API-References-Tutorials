---
title: Grupo de salto de línea de tipografía asiática
linktitle: Grupo de salto de línea de tipografía asiática
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a usar el grupo de salto de línea de tipografía asiática con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/asian-typography-line-break-group/
---

En este tutorial, le mostraremos cómo usar la función de grupo de salto de línea de tipografía asiática con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios de formato.

## Paso 1: Cargar el documento

Para comenzar, especifique el directorio para sus documentos y cargue el documento que contiene la tipografía asiática en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Paso 2: configuración de tipografía asiática

Ahora configuraremos los ajustes de tipografía asiática para el primer párrafo del documento. Así es cómo:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Paso 3: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Ejemplo de código fuente para Asian Typography Line Break Group usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Grupo de salto de línea de tipografía asiática con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Con este código, podrá aplicar el grupo de salto de línea de tipografía asiática usando Aspose.Words para .NET.

