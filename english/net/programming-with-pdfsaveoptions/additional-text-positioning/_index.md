---
title: Additional Text Positioning
linktitle: Additional Text Positioning
second_title: Aspose.Words for .NET API Reference
description: Learn how to control the placement of additional text when converting Word documents to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/additional-text-positioning/
---

In this tutorial, we'll walk you through the steps to use the additional text positioning feature with Aspose.Words for .NET. This feature allows you to control the placement of additional text when converting a Word document to PDF. Follow the steps below:

## Step 1: Loading the document

Start by uploading the Word document you want to convert to PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Be sure to specify the correct path to your Word document.

## Step 2: Set PDF Conversion Options

Create an instance of the PdfSaveOptions class and enable extra text positioning:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

This option controls the precise placement of additional text in the PDF.

## Step 3: Convert Document to PDF

Use the `Save` method to convert the Word document to PDF by specifying conversion options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Additional Text Positioning using Aspose.Words for .NET

Here is the complete source code to use the additional text positioning functionality with Aspose.Words for .NET:


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
By following these steps, you can easily control the positioning of additional text when converting a Word document to PDF with Aspose.Words for .NET.


