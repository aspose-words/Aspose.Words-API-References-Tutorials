---
title: Untangle Row Bookmarks In Word Document
linktitle: Untangle Row Bookmarks In Word Document
second_title: Aspose.Words Document Processing API
description: Untangle tangled row bookmarks in your Word documents with ease using Aspose.Words for .NET. This guide walks you through the process for cleaner and safer bookmark management.
type: docs
weight: 10
url: /net/programming-with-bookmarks/untangle-row-bookmarks/
---
## Introduction

Have you ever encountered a situation where deleting a row in a Word document by a bookmark messes up other bookmarks in adjacent rows? This can be incredibly frustrating, especially when dealing with complex tables. Thankfully, Aspose.Words for .NET offers a powerful solution: untangling row bookmarks. 

This guide will walk you through the process of untangling row bookmarks in your Word documents using Aspose.Words for .NET. We'll break down the code into easy-to-understand steps and explain each function's purpose, empowering you to tackle those pesky bookmark issues with confidence.

## Prerequisites

Before diving in, you'll need a few things:

1. Aspose.Words for .NET: This commercial library provides functionalities for working with Word documents programmatically. 2. You can download a free trial from [download link](https://releases.aspose.com/words/net/) or purchase a license from [buy](https://purchase.aspose.com/buy).
3. A C# development environment: Visual Studio or any other C# IDE will work perfectly.
4. A Word document with row bookmarks: We'll use a sample document named "Table column bookmarks.docx" for demonstration purposes.

## Import Namespaces

The first step involves importing the necessary namespaces into your C# project. These namespaces provide access to the classes and functionalities we'll be using from Aspose.Words for .NET:

```csharp
using Aspose.Words;
using System;
```

## Step 1: Load the Word Document

We begin by loading the Word document containing the tangled row bookmarks. The `Document` class handles document manipulation in Aspose.Words. Here's how to load the document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Replace with your document location
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

Remember to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your "Table column bookmarks.docx" file.

## Step 2: Untangle Row Bookmarks

This is where the magic happens! The `Untangle` function takes care of untangling the row bookmarks. Let's break down its functionality:

```csharp
private void Untangle(Document doc)
{
   foreach (Bookmark bookmark in doc.Range.Bookmarks)
   {
	   // Get the parent row of both bookmark and bookmark end
	   Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
	   Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));

	   // Check if rows are valid and adjacent
	   if (row1 != null && row2 != null && row1.NextSibling == row2)
		   // Move bookmark end to the last paragraph of the top row's last cell
		   row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
   }
}
```

Here's a step-by-step explanation of what the code does:

We iterate through all bookmarks in the document using a `foreach` loop.
For each bookmark, we retrieve the parent row of both the bookmark start (`bookmark.BookmarkStart`) and the bookmark end (`bookmark.BookmarkEnd`) using the `GetAncestor` method.
We then check if both rows are found (`row1 != null` and `row2 != null`) and if they are adjacent rows (`row1.NextSibling == row2`). This ensures we only modify bookmarks that span across adjacent rows.
If the conditions are met, we move the bookmark end node to the end of the last paragraph in the last cell of the top row (`row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd)`) effectively untangling them.

## Step 3: Delete Row by Bookmark

Now that the bookmarks are untangled, we can safely delete rows using their bookmark names. The `DeleteRowByBookmark` function handles this task:

```csharp
private void DeleteRowByBookmark(Document doc, string bookmarkName)
{
   Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

   Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
   row?.Remove();
}
```

Here's a breakdown of this function:

We take the bookmark name (`bookmarkName`) as input.
We retrieve the corresponding bookmark object using `doc.Range.Bookmarks[bookmarkName]`.
We then get the parent row of the bookmark start using `GetAncestor` (similar to the `Untangle` function).
Finally, we check if the bookmark and row exist (`bookmark != null` and

## Step 4: Verify Untangling

While the `Untangle` function should ensure the safety of other bookmarks, it's always good practice to verify. Here's how we can check if the untangling process didn't accidentally delete the end of another bookmark:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
   throw new Exception("Wrong, the end of the bookmark was deleted.");
```

This code snippet checks if the end of the bookmark named "ROW1" still exists after deleting the row with the "ROW2" bookmark. If it's null, an exception is thrown, indicating an issue with the untangling process. 

## Step 5: Save the Document

Finally, after untangling the bookmarks and potentially deleting rows, save the modified document using the `Save` method:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

This saves the document with the untangled bookmarks and any deleted rows under a new filename "WorkingWithBookmarks.UntangleRowBookmarks.docx". 

## Conclusion

By following these steps and utilizing the `Untangle` function, you can effectively untangle row bookmarks in your Word documents with Aspose.Words for .NET. This ensures that deleting rows by bookmarks doesn't cause unintended consequences with other bookmarks in adjacent rows. Remember to replace placeholders like `"YOUR DOCUMENT DIRECTORY"` with your actual paths and file names.

## FAQ's

### Is Aspose.Words for .NET free?

Aspose.Words for .NET is a commercial library with a free trial available. You can download it from [download link](https://releases.aspose.com/words/net/).

### Can I untangle row bookmarks manually in Word?

While technically possible, manually untangling bookmarks in Word can be tedious and error-prone. Aspose.Words for .NET automates this process, saving you time and effort.

### What happens if the `Untangle` function encounters an error?

The code includes an exception handler that throws an exception if the untangling process accidentally deletes the end of another bookmark. You can customize this error handling to fit your specific needs.

### Can I use this code to untangle bookmarks across non-adjacent rows?

Currently, the code focuses on untangling bookmarks that span across adjacent rows. Modifying the code to handle non-adjacent rows would require additional logic to identify and handle those scenarios.

### Are there any limitations to using this approach?

This approach assumes that bookmarks are well-defined within table cells. If bookmarks are placed outside of cells or in unexpected locations, the untangling process might not work as intended.
