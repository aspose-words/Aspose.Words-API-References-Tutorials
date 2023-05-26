---
title: Downsampling Images
linktitle: Downsampling Images
second_title: Aspose.Words for .NET API Reference
description: Learn how to reduce image resolution when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/downsampling-images/
---

In this tutorial, we'll walk you through the steps to reduce image resolution when converting to PDF with Aspose.Words for .NET. This reduces the size of the generated PDF file. Follow the steps below:

## Step 1: Loading the document

Start by uploading the document you want to convert to PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Be sure to specify the correct path to your document.

## Step 2: Configure PDF save options

Create an instance of the PdfSaveOptions class and set the image downscaling options:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

The `Resolution` property specifies the target resolution of the images and the `ResolutionThreshold` property specifies the minimum resolution below which the images will not be scaled down.

## Step 3: Convert Document to PDF

Use the `Save` method to convert the document to PDF specifying save options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Downsampling Images using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// We can set a minimum threshold for downsampling.
	// This value will prevent the second image in the input document from being downsampled.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

By following these steps, you can easily reduce image resolution when converting to PDF with Aspose.Words for .NET.



