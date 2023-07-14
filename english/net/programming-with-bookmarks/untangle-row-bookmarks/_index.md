---
title: Untangle Row Bookmarks In Word Document
linktitle: Untangle Row Bookmarks In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to untangle nested row bookmarks in word document to remove specific rows without affecting other bookmarks.
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

### FAQ's for untangle row bookmarks in word document

#### Q: Does Unscramble Row Bookmarks only work with row bookmarks in tables?

A: Yes, the Untangle Row Bookmarks feature is specifically designed to untangle row bookmarks that are in tables. This function can be used to process line bookmarks in arrays and ensure that bookmark ends are in the same line as bookmark starts.

#### Q: Does the Unscramble Line Bookmarks function modify the content of the original document?

A: Yes, the Unscramble line bookmarks function modifies the original document by moving the ends of line bookmarks to place them in the same line as the beginnings of bookmarks. Make sure to save a backup copy of the document before applying this feature.

#### Q: How can I identify line bookmarks in my Word document?

A: Row bookmarks are typically used in tables to mark specific sections. You can identify row bookmarks by browsing through bookmarks in the document and checking to see if the bookmarks are in table rows.

#### Q: Is it possible to untangle row bookmarks in non-adjacent tables?

A: The Untangle Row Bookmarks function as presented in this article is designed to untangle row bookmarks in adjacent tables. To disentangle row bookmarks in non-adjacent tables, additional adjustments to the code may be required depending on the structure of the document.

#### Q: What other manipulations can I perform on row bookmarks once they have been unraveled?

A: Once the line bookmarks are unraveled, you can perform different manipulations as needed. This may include editing, deleting, or adding content to bookmarked lines. Be sure to handle line bookmarks with care to avoid any unwanted impact on the rest of the document.
