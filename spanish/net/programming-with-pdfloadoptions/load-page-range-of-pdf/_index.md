---
title: Cargar rango de página de PDF
linktitle: Cargar rango de página de PDF
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para cargar un rango de páginas PDF específico con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

En este tutorial, lo guiaremos a través de cómo cargar un rango de páginas específico desde un documento PDF utilizando Aspose.Words para .NET. Siga los pasos a continuación:

## Paso 1: cargar un rango de páginas PDF

Use el siguiente código para cargar un rango de páginas específico desde un documento PDF:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 En este ejemplo, estamos cargando la primera página del documento PDF. Puede cambiar los valores de`PageIndex` y`PageCount` al intervalo de páginas deseado.

## Paso 2: Guardar el documento

 Finalmente, puede guardar el documento que contiene el rango de página específico usando el`Save` método:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Asegúrese de especificar la ruta correcta para guardar el documento editado.

Eso es todo ! Ahora ha cargado un rango de páginas específico desde un documento PDF usando Aspose.Words para .NET.

### Código fuente de ejemplo para Cargar rango de página de PDF usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Recuerde especificar la ruta correcta al directorio de sus documentos PDF.



