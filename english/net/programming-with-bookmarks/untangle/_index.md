---
title: Untangle
linktitle: Untangle
second_title: Aspose.Words for .NET API Reference
description: Learn how to untangle nested bookmarks in adjacent table rows using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/untangle/
---

In this article, we will explore the C# source code above to understand how to use the Untangle function in the Aspose.Words for .NET library. This function unravels nested bookmarks that are in adjacent table rows.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Browse Document Bookmarks

We use a foreach loop to loop through all the bookmarks present in the document:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Code for handling bookmarks here
}
```

## Step 2: Get parent rows from bookmarks

We use the `GetAncestor` methods to retrieve the parent rows of the bookmark's start and end nodes:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Step 3: Untangle Nested Bookmarks

If both parent lines are found and the bookmark begins and ends in adjacent lines, we move the end node of the bookmark to the end of the last paragraph of the last cell in the top row:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Example source code for Untangle using Aspose.Words for .NET

Here is the full source code example for untangling nested bookmarks using Aspose.Words for .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Get the parent row of both the bookmark and bookmark end node.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// If both rows are found okay, and the bookmark start and end are contained in adjacent rows,
		// move the bookmark end node to the end of the last paragraph in the top row's last cell.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusion

In this article, we explored the C# source code to understand how to use the Untangle function of Aspose.Words for .NET. We've followed a step-by-step guide to untangle nested bookmarks in adjacent table rows.
