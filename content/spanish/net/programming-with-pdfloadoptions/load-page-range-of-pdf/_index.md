---
title: Cargar rango de páginas de PDF
linktitle: Cargar rango de páginas de PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para cargar un rango de páginas PDF específico con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

En este tutorial, le explicaremos cómo cargar un rango de páginas específico desde un documento PDF usando Aspose.Words para .NET. Siga los pasos a continuación:

## Paso 1: cargar una variedad de páginas PDF

Utilice el siguiente código para cargar un rango de páginas específico desde un documento PDF:

```csharp
//Ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 En este ejemplo, estamos cargando la primera página del documento PDF. Puedes cambiar los valores de`PageIndex`y`PageCount` al rango de páginas deseado.

## Paso 2: guardar el documento

 Finalmente, puede guardar el documento que contiene el rango de páginas específico usando el`Save` método:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Asegúrese de especificar la ruta correcta para guardar el documento editado.

Eso es todo ! Ahora ha cargado un rango de páginas específico desde un documento PDF usando Aspose.Words para .NET.

### Código fuente de ejemplo para cargar rango de páginas de PDF usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Recuerde especificar la ruta correcta al directorio de sus documentos PDF.



