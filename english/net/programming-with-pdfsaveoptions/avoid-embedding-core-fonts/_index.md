---
title: Avoid Embedding Core Fonts
linktitle: Avoid Embedding Core Fonts
second_title: Aspose.Words for .NET API Reference
description: Learn how to avoid basic font embedding when converting Word documents to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In this tutorial, we'll walk you through the steps to use the Avoid Basic Font Embedding feature with Aspose.Words for .NET. This feature allows you to control whether basic fonts such as Arial, Times New Roman, etc. must be embedded in the PDF when converting a Word document. Follow the steps below:

## Step 1: Loading the document

Start by uploading the Word document you want to convert to PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Be sure to specify the correct path to your Word document.

## Step 2: Set PDF Conversion Options

Create an instance of the PdfSaveOptions class and enable basic font embedding avoidance:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

This option controls whether base fonts should be embedded in the PDF or not.

## Step 3: Convert Document to PDF

Use the `Save` method to convert the Word document to PDF by specifying conversion options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Avoid Embedding Core Fonts using Aspose.Words for .NET

Here is the complete source code to use the feature to avoid core font embedding with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// The output PDF will not be embedded with core fonts such as Arial, Times New Roman etc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

By following these steps, you can easily control whether base fonts should be embedded in the PDF when converting a Word document with Aspose.Words for .NET.


