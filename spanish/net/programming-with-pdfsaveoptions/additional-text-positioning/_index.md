---
title: Posicionamiento de texto adicional
linktitle: Posicionamiento de texto adicional
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a controlar la ubicación de texto adicional al convertir documentos de Word a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función de posicionamiento de texto adicional con Aspose.Words para .NET. Esta función le permite controlar la ubicación del texto adicional al convertir un documento de Word a PDF. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento de Word que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento de Word.

## Paso 2: establezca las opciones de conversión de PDF

Cree una instancia de la clase PdfSaveOptions y habilite el posicionamiento de texto adicional:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

Esta opción controla la ubicación precisa del texto adicional en el PDF.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento de Word a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para Posicionamiento de texto adicional usando Aspose.Words para .NET

Aquí está el código fuente completo para usar la funcionalidad de posicionamiento de texto adicional con Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
Siguiendo estos pasos, puede controlar fácilmente el posicionamiento del texto adicional al convertir un documento de Word a PDF con Aspose.Words para .NET.

