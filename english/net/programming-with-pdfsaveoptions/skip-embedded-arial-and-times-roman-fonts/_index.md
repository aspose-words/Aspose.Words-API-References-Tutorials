---
title: Skip Embedded Arial And Times Roman Fonts
linktitle: Skip Embedded Arial And Times Roman Fonts
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to generate PDF without embedding Arial and Times Roman fonts with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

This article provides a step-by-step guide on how to use the feature to skip embedded Arial and Times Roman fonts to metafile size with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to configure the font embedding mode option in a document and generate a PDF without embedding Arial and Times Roman fonts.

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

## Step 3: Configure save as PDF options with font embedding

To skip embedding Arial and Times Roman fonts in the generated PDF, we need to configure the `PdfSaveOptions` object and set the `FontEmbeddingMode` property to `PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Step 4: Save the document as PDF without embedded fonts

Finally, we can save the document in PDF format using the save options configured previously.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

That's all ! You have successfully generated a PDF without embedding Arial and Times Roman fonts using Aspose.Words for .NET.

### Example source code to skip embedded Arial and Times Roman fonts at metafile size with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

