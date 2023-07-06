---
title: Reduce PDF Size by Disabling Embeded Fonts
linktitle: Reduce PDF Size by Disabling Embeded Fonts
second_title: Aspose.Words for .NET API Reference
description: Learn how to reduce PDF size with disable Windows font embedding when converting documents to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In this tutorial, we'll walk you through the steps to reduce PDF size with disable Windows font embedding in a PDF document with Aspose.Words for .NET. By disabling font embedding, you can reduce the size of the generated PDF file. Follow the steps below:

## Step 1: Loading the document

Start by uploading the document you want to convert to PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Be sure to specify the correct path to your document.

## Step 2: Set PDF save options

Create an instance of the PdfSaveOptions class and specify how to embed fonts:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

This option allows you to deactivate the integration of Windows fonts in the generated PDF file.

## Step 3: Convert Document to PDF

Use the `Save` method to convert the document to PDF specifying conversion options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Disable Embed Windows Fonts using Aspose.Words for .NET

Here is the full source code to disable embedding Windows fonts in a PDF document with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// The output PDF will be saved without embedding standard windows fonts.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
By following these steps, you can easily disable the embedding of Windows fonts in a PDF document with Aspose.Words for .NET.


## Conclusion

In this tutorial, we learned how to reduce the size of a PDF file by disabling embedding Windows fonts using Aspose.Words for .NET. By disabling font embedding, you can reduce the size of the generated PDF file, making it easier to store, share, and transfer files. However, it is important to note that disabling Windows font embedding may cause appearance and formatting changes in the final PDF document. Be sure to consider these consequences when using this feature. Feel free to explore more features of Aspose.Words for .NET to optimize the generation of your PDF files.

### Frequently Asked Questions

#### Q: What is disabling Windows font embedding in a PDF document and why is it important?
A: Disabling Windows font embedding in a PDF document is the process of preventing Windows fonts from being included in the generated PDF file. This reduces the size of the PDF file by removing embedded Windows font data. This can be important for reducing the size of PDF files, which can make them easier to store, share, and transfer faster.

#### Q: How can I disable Windows font embedding in a PDF document using Aspose.Words for .NET?
A: To disable embedding Windows fonts in a PDF document using Aspose.Words for .NET, follow these steps:

Load the document you want to convert to PDF using the `Document` class and document path.

Create an instance of the `PdfSaveOptions` class and set the `FontEmbeddingMode` property to `PdfFontEmbeddingMode.EmbedNone`. This disables the embedding of Windows fonts in the generated PDF file.

Use the `Save` method of the `Document` object to convert the document to PDF specifying the conversion options configured earlier.

#### Q: What are the benefits of disabling Windows font embedding in a PDF document?
A: The benefits of disabling Windows font embedding in a PDF document are:

Reduced PDF file size: By disabling Windows font embedding, embedded Windows font data is removed, reducing the size of the generated PDF file.

Easier storage: Smaller PDF files are easier to store, save and transfer.

Faster sharing and transfer: Smaller PDF files can be shared and transferred faster, saving time and resources.

#### Q: What are the consequences of disabling Windows font embedding in a PDF document?
A: Disabling the embedding of Windows fonts in a PDF document can lead to consequences such as:

Loss of appearance and formatting: If the Windows fonts specified in the document are not available on the system where the PDF is opened, substitute fonts will be used, which may result in an incorrect appearance and formatting. different in shape from those expected.

Readability issues: If the substitute fonts used are not as readable as the original fonts, it may affect the readability of the text in the PDF document.