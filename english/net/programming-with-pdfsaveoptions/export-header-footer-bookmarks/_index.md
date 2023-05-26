---
title: Export Header Footer Bookmarks
linktitle: Export Header Footer Bookmarks
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to export header and footer bookmarks with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

This article provides a step-by-step guide on how to use the Export Header and Footer Bookmarks feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to export bookmarks from headers and footers of a document and generate a PDF with the appropriate bookmarks.

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

