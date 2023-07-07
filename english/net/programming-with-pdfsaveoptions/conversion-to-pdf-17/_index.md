---
title: Convert Word Document To PDF 1.7
linktitle: Convert Word Document To PDF 1.7
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert word document to PDF 1.7 with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

In this tutorial, we will walk you through the steps how to convert word document to PDF 1.7 with Aspose.Words for .NET. Converting to PDF 1.7 allows you to generate PDF files that conform to the PDF 1.7 standard. Follow the steps below:

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


## Conclusion

In this tutorial, we have explained how to convert a Word document to PDF 1.7 using Aspose.Words for .NET. By following the steps described, you can easily generate PDF files that comply with the PDF 1.7 standard. Be sure to specify the correct path to your Word document and configure the options for converting to PDF as needed. Conversion to PDF 1.7 ensures optimal compatibility and readability on different platforms.

### Frequently Asked Questions

#### Q: What is Word to PDF 1.7 conversion?
A: Converting Word documents to PDF 1.7 is to generate PDF files that conform to the PDF 1.7 standard. This standard specifies features and requirements for PDF files, enabling optimal compatibility and readability on different platforms.

#### Q: How can I convert a Word document to PDF 1.7 using Aspose.Words for .NET?
A: To convert a Word document to PDF 1.7 using Aspose.Words for .NET, follow these steps:

Set the directory path where your documents are located by replacing `"YOUR DOCUMENTS DIRECTORY"` with the actual path of your documents directory.

Load the Word document you want to convert to PDF using the `Document` class and specify the path to the Word document in the specified documents directory.

Configure the conversion as PDF options by creating an instance of the `PdfSaveOptions` class and specifying the version of the PDF standard you want to use using the `Compliance` property with the value `PdfCompliance. Pdf17` to generate a PDF file that conforms to the PDF 1.7 standard.

Save the document in PDF format using the `Save` method of the `Document` class specifying the path and saving options.

#### Q: What are the benefits of converting to PDF 1.7 with Aspose.Words for .NET?
A: The advantages of converting to PDF 1.7 with Aspose.Words for .NET are:

PDF 1.7 Compliant: Converting to PDF 1.7 ensures that the generated PDF file is PDF 1.7 compliant, ensuring compatibility and readability on different platforms.

Document Formatting Preservation: Aspose.Words for .NET ensures accurate Word document conversion by preserving formatting, images and styles, resulting in a true-to-original PDF file .