---
title: Pdf Render Warnings
linktitle: Pdf Render Warnings
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to dealing with PDF rendering warnings with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

This article provides a step by step guide on how to use the PDF rendering warnings feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to deal with rendering warnings when converting to PDF.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Upload the document

Next, we need to load the document we want to process. In this example, we assume the document is called "WMF with image.docx" and is located in the specified documents directory.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Step 3: Configure save as PDF options with rendering warnings

To handle rendering warnings when converting to PDF, we need to configure the `MetafileRenderingOptions` object to specify how metafiles are rendered. We also use the `HandleDocumentWarnings` option to handle the warnings generated when saving the document.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Step 4: Save document as PDF with rendering warnings

Finally, we can save the document in PDF format using the save options configured previously.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Step 5: Handle rendering warnings

Rendering warnings generated when saving the document can be retrieved using the custom warning handler. In this example, we simply print the description of each warning.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

That's all ! You have successfully handled rendering warnings when converting a document

  to PDF using Aspose.Words for .NET.

### Sample source code for PDF rendering warnings with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// If Aspose.Words cannot correctly render some of the metafile records
	// to vector graphics then Aspose.Words renders this metafile to a bitmap.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// While the file saves successfully, rendering warnings that occurred during saving are collected here.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

