---
title: Delete Row By Bookmark In Word Document
linktitle: Delete Row By Bookmark In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to delete a table row based on a specific bookmark in word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/delete-row-by-bookmark/
---

In this article, we will explore the above C# source code to understand how to use Delete Row By Bookmark function in Aspose.Words for .NET library. This feature allows you to delete a table row based on a specific bookmark in word document.

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

### FAQ's for delete row by bookmark in word document

#### Q: Can I delete multiple rows using the same bookmark?

A: Yes, you can delete multiple rows using the same bookmark. However, you need to handle the logic in your code to determine the number of rows to delete and make the adjustments necessary to the code snippet provided.

#### Q: What happens if the bookmark doesn't exist in the document?

A: If the specified bookmark doesn't exist in the document, the code snippet will return a null value for the bookmark object. Therefore, you need to handle this scenario in your code by adding appropriate checks before attempting to delete the table row.

#### Q: Is Aspose.Words library free to use?

A: Aspose.Words library is a commercial library, and you may require a valid license to use it in your projects. You can visit the official Aspose website to learn more about their licensing options and pricing.

#### Q: Can I delete rows from a table in a specific section of the Word document?

A: Yes, you can delete rows from a table in a specific section of a Word document. You can modify the code snippet provided to target a specific section by using the appropriate range or bookmark within that section.
