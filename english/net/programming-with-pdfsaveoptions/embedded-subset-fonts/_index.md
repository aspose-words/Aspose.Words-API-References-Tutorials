---
title: Embed Subset Fonts in PDF Document
linktitle: Embed Subset Fonts in PDF Document
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to embedding font subsets in a PDF document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

This article provides a step-by-step guide on how to use the font subset embedding feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to embed subsets of fonts in a document and generate a PDF containing only the glyphs used in the document.

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

## Step 3: Configure save as PDF options

To create a PDF containing only the subsets of fonts used in the document, we need to configure the `PdfSaveOptions` object with the `EmbedFullFonts` property set to `false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Step 4: Save document as PDF with font subsets

Finally, we can save the document as a PDF using the font subsets. Specify the output file name and the `saveOptions` object we configured in the previous step.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

That's all ! You have successfully embedded subsets of fonts in a document and generated a PDF containing only the glyphs used in the document with Aspose.Words for .NET.

### Sample source code for embedding font subsets with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// The output PDF will contain subsets of the fonts in the document.
	// Only the glyphs used in the document are included in the PDF fonts.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Conclusion

In this tutorial, we learned how to embed font subsets in a PDF document using Aspose.Words for .NET. Embedding subsets of fonts helps reduce the size of the PDF file while preserving the look of the document by using only the characters actually used. This ensures better compatibility and performance when viewing and printing the PDF. Feel free to further explore the features of Aspose.Words for .NET to optimize the generation of your PDF documents with embedded font subsets.

### Frequently Asked Questions

#### Q: What is embedding font subsets in a PDF document?
A: Embedding font subsets in a PDF document is the process of including only the glyphs used in the document, rather than including all complete fonts. This reduces the size of the PDF file by including only the font data necessary to display the characters actually used in the document.

#### Q: What is the difference between embedding full fonts and embedding subsets of fonts?
A: Full font embedding means including all the fonts used in the document in the PDF file, which ensures that the document will be displayed exactly as it was designed, but can increase the size of the PDF file. In contrast, embedding font subsets contains only the glyphs used in the document, thereby reducing the size of the PDF file, but limiting the ability to exactly replicate the look of the document if additional characters are added later.

#### Q: How can I embed font subsets in a PDF document using Aspose.Words for .NET?
A: To embed font subsets in a PDF document using Aspose.Words for .NET, follow these steps:

Set the document directory path by replacing `"YOUR DOCUMENT DIRECTORY"` with the actual path of your documents directory.

Load the document you want to process using the `Document` class and the document path.

Configure PDF save options by creating an instance of the `PdfSaveOptions` class and setting the `EmbedFullFonts` property to `false`. This ensures that only the font subsets used in the document will be included in the PDF file.

Save the document in PDF format with the font subsets embedded using the `Save` method of the `Document` object, specifying the name of the output file and the save options configured earlier.

#### Q: What are the benefits of embedding font subsets in a PDF document?
A: The benefits of embedding font subsets in a PDF document are:

Reduced PDF file size: By including only the glyphs used in the document, the PDF file size is reduced compared to embedding full fonts.

Preservation of the appearance of the document: The subsets of fonts included in the PDF file make it possible to reproduce the appearance of the document using only the characters actually used.

Compatibility with the restrictions of License: Embedding subsets of fonts may be preferred in cases where full fonts cannot be legally embedded due to licensing restrictions.