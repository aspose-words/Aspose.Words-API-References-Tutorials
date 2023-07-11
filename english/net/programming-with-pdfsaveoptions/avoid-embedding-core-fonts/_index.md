---
title: Reduce PDF File Size by Not Embedding Core Fonts
linktitle: Reduce PDF File Size by Not Embedding Core Fonts
second_title: Aspose.Words Document Processing API
description: Learn how to Reduce PDF File Size by Not Embedding Core Fonts when converting Word documents to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In this tutorial, we'll walk you through the steps how to reduce PDF file size by not embedding core fonts with Aspose.Words for .NET. This feature allows you to control whether basic fonts such as Arial, Times New Roman, etc. must be embedded in the PDF when converting a Word document. Follow the steps below:

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


## Conclusion

In this tutorial, we explained how to reduce the size of a PDF file by not embedding basic fonts with Aspose.Words for .NET. This feature lets you control whether base fonts should be embedded in the PDF when converting a Word document. By following the steps outlined, you can easily control the embedding or non-embedding of basic fonts, which can help reduce PDF file size and ensure better compatibility and a consistent look of the document on different devices and platforms. Don't forget to consider the consequences of not embedding base fonts and to experiment to ensure that the document renders as expected.

### Frequently Asked Questions

#### Q: What is the option to not embed base fonts in a PDF file and why is it important?
A: The option to not embed base fonts in a PDF file controls whether base fonts such as Arial, Times New Roman, etc. must be embedded in the PDF when converting a Word document. This can be important to reduce the size of the PDF file by avoiding including fonts commonly available on PDF reader systems. It can also help ensure better compatibility and consistent appearance of the PDF document across different devices and platforms.

#### Q: How can I configure Aspose.Words for .NET not to embed base fonts in a PDF file?
A: To configure Aspose.Words for .NET to not embed core fonts in a PDF file, follow these steps:

Set the directory path where your documents are located by replacing `"YOUR DOCUMENTS DIRECTORY"` with the actual path of your documents directory.

Load the Word document you want to convert to PDF using the `Document` class and the specified document path.

Create an instance of the `PdfSaveOptions` class and set the `UseCoreFonts` property to `true`. This will avoid the embedding of base fonts in the generated PDF file.

Use the `Save` method of the `Document` object to save the document in PDF format specifying the conversion options configured earlier.

#### Q: What are the benefits of not embedding base fonts in a PDF file?
A: The benefits of not embedding base fonts in a PDF file are:

PDF file size reduction: By avoiding embedding commonly available fonts like Arial, Times New Roman, etc., the PDF file size can be reduced, making it easier to store, share and transfer files .

Better compatibility: By using basic fonts commonly available on PDF reader systems, you ensure better compatibility and document appearance on different devices and platforms.

#### Q: What are the consequences of not embedding base fonts in a PDF file?
A: The consequences of not embedding base fonts in a PDF file are as follows:

Different appearance: If the base fonts are not available on the system where the PDF is opened, substitute fonts will be used, which may result in a different appearance than intended.

Readability issues: Substitute fonts used may not be as legible as the original fonts, which may affect the readability of the document.