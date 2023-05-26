---
title: Conversion To Pdf 17
linktitle: Conversion To Pdf 17
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert documents to PDF 1.7 with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

In this tutorial, we will walk you through the steps to convert to PDF 1.7 with Aspose.Words for .NET. Converting to PDF 1.7 allows you to generate PDF files that conform to the PDF 1.7 standard. Follow the steps below:

## Step 1: Loading the document

Start by uploading the document you want to convert to PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Be sure to specify the correct path to your document.

## Step 2: Set PDF Conversion Options

Create an instance of the PdfSaveOptions class and specify the version of the PDF standard you want to use:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

This option ensures that the generated PDF file conforms to the PDF 1.7 standard.

## Step 3: Convert Document to PDF

Use the `Save` method to convert the document to PDF specifying conversion options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Conversion To Pdf 17 using Aspose.Words for .NET

Here is the complete source code to convert to PDF 1.7 with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

By following these steps, you can easily convert to PDF 1.7 with Aspose.Words for .NET.


