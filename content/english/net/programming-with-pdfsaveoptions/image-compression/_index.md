---
title: Image Compression in a PDF Document
linktitle: Image Compression in a PDF Document
second_title: Aspose.Words Document Processing API
description: Step by step guide to compression images in a PDF Document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/image-compression/
---

This article provides a step by step guide on how to use the Image Compression in a PDF Document feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to compress images in a document and generate a PDF with proper image compression.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Upload the document

Next, we need to load the document we want to process. In this example, we assume the document is called "Rendering.docx" and is located in the specified documents directory.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 3: Configure save as PDF options with image compression

To compress images when converting to PDF, we need to configure the `PdfSaveOptions` object. We can set image compression type, JPEG quality and other PDF compliance options if required.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Step 4: Save document as PDF with image compression

Finally, we can save the document in PDF format using the save options configured previously.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Step 5: Configure options for saving to PDF/A-2u with image compression

If you want to generate PDF/A-2u compliant PDF with image compression, you can configure the additional saving options.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Use JPEG compression with 50% quality to reduce file size.
};
```

## Step 6: Save the document as PDF/A-2u with image compression

Save the document in PDF/A-2u format using the additional save options configured earlier.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



That's all ! You have successfully compressed the images in a document and generated a PDF with proper image compression using Aspose.Words for .NET.

### Sample source code for compressing images with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Use JPEG compression at 50% quality to reduce file size.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Conclusion

In this tutorial, we explained how to compress images in a PDF document using Aspose.Words for .NET. By following the steps described, you can easily reduce the size of images in your PDF document and generate a PDF with proper image compression. Use the image compression features of Aspose.Words for .NET to optimize the size of your PDF documents while preserving image quality.

### Frequently Asked Questions

#### Q: What is image compression in a PDF document?
A: Compressing images in a PDF document is to reduce the size of the images included in the PDF document to reduce the overall size of the PDF file. This reduces the storage space needed and improves performance when loading and viewing the PDF.

#### Q: How can I compress images in a PDF document with Aspose.Words for .NET?
A: To compress images in a PDF document with Aspose.Words for .NET, follow these steps:

Create an instance of the `Document` class specifying the path to the Word document.

Create an instance of the `PdfSaveOptions` class and set the `ImageCompression` property to `PdfImageCompression.Jpeg` to use JPEG compression.

You can also set other image compression options, such as JPEG quality, according to your needs.

Use the `Save` method of the `Document` class to save the document in PDF format by specifying save options.

#### Q: What is the difference between standard image compression and PDF/A-2u image compression?
A: Standard image compression reduces the size of images in a PDF document while preserving form fields. This reduces the overall size of the PDF file without compromising form field functionality.

Image Compression with PDF/A-2u is an additional option that allows you to generate a PDF file that conforms to the PDF/A-2u standard while applying image compression. PDF/A-2u is an ISO standard for archival PDF documents and guarantees the long-term preservation of documents.

