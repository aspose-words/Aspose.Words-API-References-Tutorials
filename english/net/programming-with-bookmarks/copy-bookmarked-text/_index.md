---
title: Copy Bookmarked Text
linktitle: Copy Bookmarked Text
second_title: Aspose.Words for .NET API Reference
description: Learn how to copy bookmark text from a source document to another document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/copy-bookmarked-text/
---

In this article, we will explore the C# source code above to understand how to use the Copy Bookmarked Text function in the Aspose.Words for .NET library. This feature allows you to copy the contents of a specific bookmark from a source document to another document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Loading Source Document

Before copying the bookmark text, we need to load the source document into a `Document` object using the file path:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Step 2: Getting source bookmark

We use the `Bookmarks` property of the source document range to get the specific bookmark we want to copy:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Step 3: Creating the destination document

We create a new document that will serve as the destination document to copy the bookmark content:

```csharp
Document dstDoc = new Document();
```

## Step 4: Specifying the Copy Location

We specify the location where we want to add the copied text. In our example, we add the text to the end of the body of the last section of the destination document:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Step 5: Import and copy bookmark text

We use a `NodeImporter` object to import and copy bookmark text from a source document to the destination document:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Example source code for Copy Bookmarked Text using Aspose.Words for .NET

Here is the full example source code to demonstrate copying text from a bookmark using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// This is the bookmark whose content we want to copy.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// We will be adding to this document.
	Document dstDoc = new Document();

	// Let's say we will be appended to the end of the body of the last section.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// If you import multiple times without a single context, it will result in many styles created.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Conclusion

In this article, we explored the C# source code to understand how to use the function Copy Bookmarked Text from Aspose.Words for .NET. We followed a step-by-step guide to copy the contents of a bookmark from a source document to another document.
