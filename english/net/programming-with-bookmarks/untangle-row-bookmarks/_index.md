---
title: Untangle Row Bookmarks
linktitle: Untangle Row Bookmarks
second_title: Aspose.Words for .NET API Reference
description: Learn how to untangle nested row bookmarks to remove specific rows without affecting other bookmarks.
type: docs
weight: 10
url: /net/programming-with-bookmarks/untangle-row-bookmarks/
---

In this article, we will explore the C# source code above to understand how to use the Untangle Row Bookmarks function in the Aspose.Words for .NET library. This function makes it possible to put the ends of bookmarks of lines in the same line as the beginnings of bookmarks.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Loading the document

We use the `Document` class to load the existing document from a file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Step 2: Unravel Line Bookmarks

We use the `Untangle` function to untangle bookmarks from rows. This function performs the custom task of putting the bookmark ends of lines in the same line as the bookmark starts:

```csharp
Untangle(doc);
```

## Step 3: Delete line by bookmark

We use the `DeleteRowByBookmark` function to delete a specific row by its bookmark:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Step 4: Check integrity of other bookmarks

We verify that the other bookmarks have not been damaged by checking if the end of the bookmark is still present:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Example source code for Untangle Row Bookmarks using Aspose.Words for .NET**

Here is the full sample source code to untangle bookmarks from lines using Aspose.Words for .NET:


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	// This performs the custom task of putting the row bookmark ends into the same row with the bookmark starts.
	Untangle(doc);

	// Now we can easily delete rows by a bookmark without damaging any other row's bookmarks.
	DeleteRowByBookmark(doc, "ROW2");

	// This is just to check that the other bookmark was not damaged.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Conclusion

In this article, we explored the C# source code to understand how to use the Untangle Row Bookmarks feature of Aspose.Words for .NET. We followed a step-by-step guide to untangle row bookmarks and delete a specific row without damage other bookmarks.
