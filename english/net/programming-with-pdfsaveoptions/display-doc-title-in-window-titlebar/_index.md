---
title: Display Doc Title In Window Titlebar
linktitle: Display Doc Title In Window Titlebar
second_title: Aspose.Words for .NET API Reference
description: Learn how to display document title in window title bar when converting to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

In this tutorial, we will guide you through the steps to display document title in window title bar with Aspose.Words for .NET. This feature allows you to display the document title in the window title bar when you open the generated PDF document. Follow the steps below:

## Step 1: Loading the document

Start by uploading the document you want to convert to PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Be sure to specify the correct path to your document.

## Step 2: Configure PDF Save Options

Create an instance of the PdfSaveOptions class and enable the display of the document title in the window title bar:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

This option enables the display of the document title in the window title bar when converting to PDF.

## Step 3: Convert Document to PDF

Use the `Save` method to convert the document to PDF specifying conversion options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Display Doc Title In Window Titlebar using Aspose.Words for .NET

Here is the full source code to display document title in window title bar in a PDF document with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
By following these steps, you can easily display the document title in the window title bar when converting to PDF with Aspose.Words for .NET.


