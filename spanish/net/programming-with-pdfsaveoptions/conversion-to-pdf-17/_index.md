---
title: Conversión a PDF 17
linktitle: Conversión a PDF 17
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos a PDF 1.7 con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

En este tutorial, lo guiaremos a través de los pasos para convertir a PDF 1.7 con Aspose.Words para .NET. La conversión a PDF 1.7 le permite generar archivos PDF que cumplen con el estándar PDF 1.7. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: establezca las opciones de conversión de PDF

Cree una instancia de la clase PdfSaveOptions y especifique la versión del estándar de PDF que desea utilizar:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Esta opción garantiza que el archivo PDF generado cumpla con el estándar PDF 1.7.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Ejemplo de código fuente para la conversión a PDF 17 usando Aspose.Words para .NET

Aquí está el código fuente completo para convertir a PDF 1.7 con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Siguiendo estos pasos, puede convertir fácilmente a PDF 1.7 con Aspose.Words para .NET.

