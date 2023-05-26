---
title: Embedded All Fonts
linktitle: Embedded All Fonts
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to embed all fonts in a PDF using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

This article provides a step-by-step guide on how to use the Embedded All Fonts feature of Aspose.Words for .NET. We will walk through the code snippet and explain each part in detail. By the end of this tutorial, you will be able to understand how to embed all fonts in a document and generate a PDF with the embedded fonts using Aspose.Words for .NET.

Before we begin, make sure you have the Aspose.Words for .NET library installed and set up in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory path

To get started, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the document

Next, we need to load the document that we want to process. In this example, we assume that the document is named "Rendering.docx" and is located in the specified document directory.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 3: Configure the PDF save options

To embed all fonts in the resulting PDF, we need to configure the `PdfSaveOptions` object with the `EmbedFullFonts` property set to `true`. This ensures that all fonts used in the document are included in the generated PDF file.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## Step 4: Save the document as PDF with embedded fonts

Finally, we can save the document as a PDF file with the embedded fonts. Specify the output file name, and the `saveOptions` object we configured in the previous step.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

That's it! You have successfully embedded all fonts in a document and generated a PDF with the embedded fonts using Aspose.Words for .NET.

### Example source code for Embedded All Fonts using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// The output PDF will be embedded with all fonts found in the document.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Conclusion

In this tutorial, we have covered the step-by-step process of using the Embedded All Fonts feature of Aspose.Words for .NET. We learned how to load a document, configure the PDF save options, and save the document as a PDF file with embedded fonts. By following this guide, you can ensure that your PDF documents have all the necessary fonts embedded, providing consistent and accurate rendering across different devices and platforms.

