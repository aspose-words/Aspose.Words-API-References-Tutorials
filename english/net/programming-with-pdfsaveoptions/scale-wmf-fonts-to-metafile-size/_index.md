---
title: Reduce PDF Size with Scale Wmf Fonts To Metafile Size
linktitle: Reduce PDF Size with Scale Wmf Fonts To Metafile Size
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to reduce pdf size with scale wmf fonts to metafile size size when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

This article provides a step-by-step guide on how to reduce pdf size with scale wmf fonts to metafile size feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to enable or disable WMF font scaling when converting to PDF.

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

## Conclusion

In this tutorial, we explained how to enable or disable resizing of WMF fonts to metafile size in a PDF document using Aspose.Words for .NET. By following the steps described, you can easily control whether WMF fonts should be resized to match the metafile size when converting to a PDF document. This can help you reduce the size of the generated PDF file and improve rendering performance. Be sure to specify the correct path to your documents and configure the metafile rendering options as needed.

### Frequently Asked Questions

#### Q: What is resizing WMF fonts to metafile size in a PDF document?
A: Resizing WMF fonts to metafile size in a PDF document is a feature that controls whether WMF fonts should be scaled to match the metafile size when converting to a PDF document. When this feature is enabled, WMF fonts are scaled to match the size of the metafile, which may reduce the size of the generated PDF document.

#### Q: How can I use Aspose.Words for .NET to enable or disable resizing of WMF fonts to metafile size in a PDF document?
A: To enable or disable resizing of WMF fonts to metafile size in a PDF document using Aspose.Words for .NET, follow these steps:

Set the directory path where your documents are located by replacing `"YOUR DOCUMENT DIRECTORY"` with the actual path of your documents directory.

Load the document you want to process using the `Document` class and specify the path to the Word document in the specified documents directory.

Configure metafile rendering options by creating an instance of the `MetafileRenderingOptions` class and setting the `ScaleWmfFontsToMetafileSize` property to `true` to enable scaling of WMF fonts to metafile size, or to `false` to disable this feature.

Configure the save as PDF options by creating an instance of the `PdfSaveOptions` class and using the metafile rendering options configured earlier.

Save the document in PDF format using the `Save` method of the `Document` class specifying the path and saving options.

#### Q: What are the benefits of resizing WMF fonts to metafile size in a PDF document?
A: The advantages of resizing WMF fonts to metafile size in a PDF document are:

PDF file size reduction: Resizing WMF fonts to metafile size can reduce the size of the generated PDF document by adapting the font size to the metafile needs.

Improved performance: By adjusting the size of WMF fonts to the dimensions of the metafile, the rendering of the PDF document can be faster and more efficient.