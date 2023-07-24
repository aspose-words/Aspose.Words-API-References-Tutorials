---
title: Export Word Document Header Footer Bookmarks to PDF Document
linktitle: Export Word Document Header Footer Bookmarks to PDF Document
second_title: Aspose.Words Document Processing API
description: Step by step guide to export word document header footer bookmarks to pdf document bookmarks with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

This article provides a step-by-step guide on how to export word document header footer bookmarks to pdf document feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to export bookmarks from headers and footers of a document and generate a PDF with the appropriate bookmarks.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Upload the document

Next, we need to load the document we want to process. In this example, we assume the document is called "Bookmarks in headers and footers.docx" and is located in the specified documents directory.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Step 3: Configure save as PDF options

To export header and footer bookmarks, we need to configure the `PdfSaveOptions` object. In this example, we set the default bookmark outline level to 1 and the header and footer bookmark export mode to "First".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Step 4: Save the document as PDF with headers and footers bookmarks

Finally, we can save the document in PDF format using the save options configured previously.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

That's all ! You have successfully exported header and footer bookmarks from a document and generated a PDF with the appropriate bookmarks using Aspose.Words for .NET.

### Sample source code for exporting header and footer bookmarks with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Conclusion

In this tutorial, we explained how to export header and footer bookmarks from a Word document to a PDF document using Aspose.Words for .NET. Exported bookmarks allow easy navigation and quick reference to corresponding headers and footers in the generated PDF document. Follow the steps described to export header and footer bookmarks from a document and generate a PDF with the appropriate bookmarks using Aspose.Words for .NET. Be sure to specify the correct path to your documents and configure save options as needed.

### Frequently Asked Questions

### Q: What is exporting header and footer bookmarks from a Word document to a PDF document?
A: Exporting header and footer bookmarks from Word document to PDF document is a feature to keep and generate bookmarks in the PDF document from the headers and footers. footers of the original Word document. This allows users to quickly and easily navigate through the PDF document by using bookmarks corresponding to headers and footers.

### Q: How can I use Aspose.Words for .NET to export header and footer bookmarks from a Word document to a PDF document?
A: To export header and footer bookmarks from a Word document to a PDF document using Aspose.Words for .NET, follow these steps:

Set the directory path where your documents are located by replacing `"YOUR DOCUMENT DIRECTORY"` with the actual path of your documents directory.

Load the document you want to process using the `Document` class and specify the path to the Word document in the specified documents directory.

Configure save as PDF options by creating an instance of the `PdfSaveOptions` class and setting the appropriate header and footer bookmark options.

Save the document in PDF format using the `Save` method of the `Document` class specifying the path and saving options.

### Q: What are the benefits of exporting header and footer bookmarks to a PDF document?
A: The advantages of exporting header and footer bookmarks into a PDF document are:

Easy Navigation: Bookmarks allow users to easily navigate a PDF document by referring to specific headers and footers.

Quick Reference: Bookmarks allow users to quickly find relevant sections of the PDF document based on headers and footers.