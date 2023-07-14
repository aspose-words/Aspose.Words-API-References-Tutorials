---
title: Display Document Title In Window Titlebar
linktitle: Display Document Title In Window Titlebar
second_title: Aspose.Words Document Processing API
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

### Frequently Asked Questions

#### Q: What is the "Show document title in window title bar" feature with Aspose.Words for .NET?
The "Show document title in window title bar" feature with Aspose.Words for .NET allows you to display the document title in the window title bar when you open the generated PDF document. This makes it easier to identify and distinguish PDF documents in your reading environment.

#### Q: How can I use this feature with Aspose.Words for .NET?
To use this feature with Aspose.Words for .NET, follow these steps:

Load the document using the `Document` method and specifying the path of the file to convert to PDF.

Configure PDF save options by creating an instance of the `PdfSaveOptions` class and setting the `DisplayDocTitle` property to `true`. This enables the display of the document title in the window title bar when converting to PDF.

Use the `Save` method to convert the document to PDF specifying the conversion options.

#### Q: Does this feature change the content of the document itself?
No, this feature does not modify the content of the document itself. It only affects the display of the document title in the window title bar when it is opened as a PDF document. The content of the document remains unchanged.

#### Q: Is it possible to customize the title of the document displayed in the title bar of the window?
Yes, you can customize the document title displayed in the window title bar by changing the `Document.Title` property of the document before converting it to PDF. You can set the desired title using a string. Be sure to set the title before calling the `Save` method for converting to PDF.

#### Q: What other output formats does Aspose.Words support for document conversion?
Aspose.Words for .NET supports many output formats for document conversion, such as PDF, XPS, HTML, EPUB, MOBI, image (JPEG, PNG, BMP, TIFF, GIF), and many more. still others. You can choose the appropriate output format according to your specific needs.
