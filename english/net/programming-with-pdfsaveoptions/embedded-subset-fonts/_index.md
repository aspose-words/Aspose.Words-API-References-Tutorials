---
title: Embedded Subset Fonts
linktitle: Embedded Subset Fonts
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to embedding font subsets in a PDF using Aspose.Words for .NET.
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

