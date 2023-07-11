---
title: Optimize PDF Size with Skip Embedded Arial & Times Roman Fonts
linktitle: Optimize PDF Size with Skip Embedded Arial & Times Roman Fonts
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to generate optimized PDF without embedding Arial and Times Roman fonts with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

This article provides a step-by-step guide on how to use the feature to optimize PDF size by skipping embedded Arial and Times Roman fonts to metafile size with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to configure the font embedding mode option in a document and generate a PDF without embedding Arial and Times Roman fonts.

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

## Conclusion

In this tutorial, we explained how to disable the embedding of Arial and Times Roman fonts in a PDF document using Aspose.Words for .NET. By following the steps outlined, you can generate a PDF file without embedding these specific fonts, which can help reduce file size and ensure better document compatibility across different platforms. Be sure to consider the consequences of disabling font embedding when using this feature. Feel free to explore more features of Aspose.Words for .NET to optimize the generation of your PDF files.

### Frequently Asked Questions

#### Q: What is disabling Arial and Times Roman font embedding in a PDF document and why is it important?
A: Disabling the embedding of Arial and Times Roman fonts in a PDF document is the process of not including these fonts in the generated PDF file. This can be important to reduce the size of the PDF file by avoiding including fonts that are already commonly available on PDF reader systems. It can also help ensure better compatibility and consistent appearance of the PDF document across different devices and platforms.

#### Q: How can I configure Aspose.Words for .NET not to embed Arial and Times Roman fonts in a PDF document?
A: To configure Aspose.Words for .NET to not embed Arial and Times Roman fonts in a PDF document, follow these steps:

Set the directory path where your documents are located by replacing `"YOUR DOCUMENT DIRECTORY"` with the actual path of your documents directory.

Load the document you want to process using the `Document` class and the specified document path.

Create an instance of the `PdfSaveOptions` class and set the `FontEmbeddingMode` property to `PdfFontEmbeddingMode.EmbedAll`. This will embed all fonts except Arial and Times Roman in the generated PDF file.

Use the `Save` method of the `Document` object to save the document in PDF format specifying the save options configured earlier.

#### Q: What are the benefits of disabling Arial and Times Roman font embedding in a PDF document?
A: The benefits of disabling Arial and Times Roman font embedding in a PDF document are:

PDF file size reduction: By avoiding embedding commonly available fonts like Arial and Times Roman, PDF file size can be reduced, making it easier to store, share and transfer files.

Better compatibility: By using fonts that are commonly available on PDF reader systems, you ensure better compatibility and look of the document on different devices and platforms.

#### Q: What are the consequences of disabling the embedding of Arial and Times Roman fonts in a PDF document?
A: The consequences of disabling the embedding of Arial and Times Roman fonts in a PDF document are as follows:

Different appearance: If Arial and Times Roman fonts are not available on the system where the PDF is opened, substitute fonts will be used, which may result in a different appearance than intended.

Readability issues: Substitute fonts used may not be as readable as the fonts in origin, which may affect the readability of the document.