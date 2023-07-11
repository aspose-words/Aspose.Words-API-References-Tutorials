---
title: Copy Bookmarked Text In Word Document
linktitle: Copy Bookmarked Text In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to copy bookmark text in word document to another document using Aspose.Words for .NET.
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

### FAQ's for copy bookmarked text in word document

#### Q: What are the requirements to use the "Copy text with bookmarks" feature in Aspose.Words for .NET?

A: To use the "Copy text with bookmarks" feature in Aspose.Words for .NET, you need to have basic knowledge of C# language. You also need a .NET development environment with the Aspose.Words library installed.

#### Q: How do I load a source document into Aspose.Words for .NET?

A: To load a source document in Aspose.Words for .NET, you can use the `Document` class by specifying the file path of the document. Here is a sample code:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Q: How to get the content of a specific bookmark in a source document using Aspose.Words for .NET?

A: To get the contents of a specific bookmark in a source document using Aspose.Words for .NET, you can access the `Bookmarks` property of the source document range and use the bookmark name to retrieve the specific bookmark . Here is a sample code:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Q: How to specify the location of the bookmark text copy in a destination document using Aspose.Words for .NET?

A: To specify where you want to add copied bookmark text in a destination document using Aspose.Words for .NET, you can navigate to the body of the last section of the destination document. You can use the `LastSection` property to access the last section and the `Body` property to access the body of that section. Here is a sample code:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Q: How to import and copy bookmark text from source document to destination document using Aspose.Words for .NET?

A: To import and copy bookmark text from a source document to a destination document using Aspose.Words for .NET, you can use the `NodeImporter` class specifying the source document, destination document and the formatting mode to keep. Then you can use the `AppendBookmarkedText` method to add the bookmark text in the destination document. Here is a sample code:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Q: How to save a destination document after copying bookmark text using Aspose.Words for .NET?

A: To save a destination document after copying text from a bookmark using Aspose.Words for .NET, you can use the `Save` method of the `Document` object specifying the destination file path. Here is a sample code:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```
