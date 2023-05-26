---
title: Create Bookmark
linktitle: Create Bookmark
second_title: Aspose.Words for .NET API Reference
description: Learn how to create bookmarks in a document and specify bookmark preview levels in a PDF using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/create-bookmark/
---

In this article, we will explore the C# source code above to understand how to use the Create Bookmark function in the Aspose.Words for .NET library. This feature allows you to create bookmarks in a document and specify bookmark preview levels in an output PDF file.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating the Document and Generator

Before creating bookmarks, we need to create a document and a document builder using the `Document` and `DocumentBuilder` objects:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Creating the main bookmark

We use the `StartBookmark` method to start a main bookmark and the `EndBookmark` method to end it. In between, we can add text and other bookmarks:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Add more bookmarks or text here.

builder. EndBookmark("My Bookmark");
```

## Step 3: Creating Nested Bookmarks

We can also create nested bookmarks inside a main bookmark. We use the same `StartBookmark` and `EndBookmark` methods to create and end nested bookmarks:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Step 4: Specifying bookmark preview levels in the output PDF file

We use the `PdfSaveOptions` object to specify the bookmark preview levels in the output PDF file. We use the `BookmarksOutlineLevels` property

  to add main bookmarks and nested bookmarks with their respective levels:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Example source code for Create Bookmark using Aspose.Words for .NET

Here is the full example source code to demonstrate creating bookmarks using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Create Bookmark function of Aspose.Words for .NET. We've followed a step-by-step guide to creating bookmarks in a document and specifying bookmark preview levels in an output PDF file.
