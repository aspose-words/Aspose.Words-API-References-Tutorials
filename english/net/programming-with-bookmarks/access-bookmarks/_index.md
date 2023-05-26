---
title: Access Bookmarks
linktitle: Access Bookmarks
second_title: Aspose.Words for .NET API Reference
description: Learn how to access bookmarks in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/access-bookmarks/
---

In this article, we will explore the C# source code above to understand how to use Access Bookmarks function in Aspose.Words for .NET library. This feature provides access to specific bookmarks in a Word document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Loading the document

Before we start accessing bookmarks, we need to load a Word document using Aspose.Words for .NET. This can be done by instantiating a `Document` object specifying the document file path:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Step 2: Access to bookmarks

Once the document is loaded, we can access the bookmarks in the document. There are two ways to access bookmarks: by index and by name.

- Access by index: In our example, we use index 0 to access the first bookmark of the document:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Access by name: In our example, we use the name "MyBookmark3" to access a specific bookmark in the document:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Example source code for Access Bookmarks using Aspose.Words for .NET

Here is the full example source code to demonstrate accessing bookmarks using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// By index:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// By name:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Access Bookmarks feature of Aspose.Words for .NET. We followed a step-by-step guide to upload a document and access bookmarks using index and name.
