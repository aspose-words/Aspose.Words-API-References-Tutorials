---
title: Disable Embed Windows Fonts
linktitle: Disable Embed Windows Fonts
second_title: Aspose.Words for .NET API Reference
description: Learn how to disable Windows font embedding when converting documents to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In this tutorial, we'll walk you through the steps to disable Windows font embedding in a PDF document with Aspose.Words for .NET. By disabling font embedding, you can reduce the size of the generated PDF file. Follow the steps below:

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


