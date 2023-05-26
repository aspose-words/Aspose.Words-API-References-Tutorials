---
title: Delete Row By Bookmark
linktitle: Delete Row By Bookmark
second_title: Aspose.Words for .NET API Reference
description: Learn how to delete a table row based on a specific bookmark in a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/delete-row-by-bookmark/
---

In this article, we will explore the above C# source code to understand how to use Delete Row By Bookmark function in Aspose.Words for .NET library. This feature allows you to delete a table row based on a specific bookmark in a document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Getting the bookmark

We use the `Bookmarks` property of the document range to get the specific bookmark we want to use to delete the table row:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Step 2: Deleting the table row

We use the `GetAncestor` method to get the `Row` type parent element of the bookmark. Next, we use the `Remove` method to remove the table row:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Example source code for Delete Row By Bookmark using Aspose.Words for .NET

Here is the full sample source code to demonstrate deleting a table row based on a specific bookmark using Aspose.Words for .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusion

In this article, we have explored the C# source code to understand how to use the Delete Row By Bookmark function of Aspose.Words for .NET. We followed a step-by-step guide to delete a table row based on a specific bookmark in a document.
