---
title: Scale Wmf Fonts To Metafile Size
linktitle: Scale Wmf Fonts To Metafile Size
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to adjust WMF font size when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

This article provides a step-by-step guide on how to use the WMF Font Scaling to Metafile Size feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to enable or disable WMF font scaling when converting to PDF.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Upload the document

Next, we need to load the document we want to process. In this example, we assume the document is called "WMF with text.docx" and is located in the specified documents directory.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Step 3: Configure metafile rendering options

To enable or disable WMF font scaling to metafile size, we need to configure the `MetafileRenderingOptions` object. In this example, we disable font scaling by setting the `ScaleWmfFontsToMetafileSize` property to `false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Step 4: Configure save as PDF options with metafile rendering options

Finally, we can configure the save-to-PDF options using the metafile rendering options configured earlier.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Step 5: Save Document as PDF with Metafile Rendering Options

Save the document in PDF format using the previously configured save options.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

That's all ! You have successfully enabled or disabled WMF font scaling to metafile size when converting

a PDF document using Aspose.Words for .NET.

### Example source code for scaling WMF fonts to metafile size with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// If Aspose.Words cannot correctly render some of the metafile records to vector graphics
	// then Aspose.Words renders this metafile to a bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

