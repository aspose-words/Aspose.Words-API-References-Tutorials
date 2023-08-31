---
title: Reduce PDF Document Size with Downsampling Images
linktitle: Reduce PDF Document Size with Downsampling Images
second_title: Aspose.Words Document Processing API
description: Learn how to reduce pdf document size with downsampling images when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/downsampling-images/
---

In this tutorial, we'll walk you through the steps to reduce pdf document size with downsampling images when converting to PDF with Aspose.Words for .NET. This reduces the size of the generated PDF file. Follow the steps below:

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

## Conclusion

In this tutorial, we have explained how to reduce the size of a PDF document with image sampling when converting to PDF using Aspose.Words for .NET. By following the steps described, you can easily reduce the resolution of images and the size of the generated PDF file. Be sure to specify the correct path to your document and configure the image sampling options as needed. Reducing the PDF file size makes it easier to share, store and quickly load the file on different platforms. Enjoy the benefits of reducing PDF document size with image sampling using Aspose.Words for .NET.

### Frequently Asked Questions

#### Q: What is reducing the size of the PDF document with image sampling?
A: Reducing PDF document size with Image Sampling is to decrease the size of the generated PDF file by reducing the resolution of the images when converting to PDF. This optimizes the use of storage space and makes it easier to share and transfer the PDF file.

#### Q: How can I reduce PDF document size with image sampling using Aspose.Words for .NET?
A: To reduce PDF document size with image sampling using Aspose.Words for .NET, follow these steps:

Set the directory path where your documents are located by replacing `"YOUR DOCUMENTS DIRECTORY"` with the actual path of your documents directory.

Load the document you want to convert to PDF using the `Document` class and specify the path to the document in the specified documents directory.

Configure save as PDF options by creating an instance of the `PdfSaveOptions` class and setting the image sampling options using the `DownsampleOptions` property. You can specify the target resolution of images using the `Resolution` property and set a minimum resolution threshold above which images will not be scaled down using the `ResolutionThreshold` property.

Save the document in PDF format using the `Save` method of the `Document` class specifying the path and saving options.

#### Q: What are the benefits of reducing PDF document size with image sampling?
A: The benefits of reducing PDF document size with image sampling are:

Reduced PDF file size: Image sampling reduces the resolution of images in the PDF document, resulting in a significant decrease in PDF file size. This makes it easy to share and transfer the file, especially via email or online.

Optimization of storage space: Reducing the size of the PDF file helps to optimize the use of storage space, especially when you have many PDF files containing high resolution images.

Performance improvements: Smaller PDF files load faster and can be opened and viewed faster on different devices.