---
title: Bookmark Table Columns
linktitle: Bookmark Table Columns
second_title: Aspose.Words for .NET API Reference
description: Learn how to bookmark a table column in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/bookmark-table-columns/
---

In this article, we will explore the C# source code above to understand how to use the Bookmark Table Columns function in the Aspose.Words for .NET library. This feature allows you to bookmark a specific column of a table in a Word document and access the content of that column.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating the table

Before creating a bookmark on a table column, we must first create the table using a `DocumentBuilder` object. In our example, we create a table with two rows and two columns:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Step 2: Creating the column bookmark

We use the `StartBookmark` method to create a bookmark on a specific column of the table. In our example, we use the name "MyBookmark" for the bookmark:

```csharp
builder. StartBookmark("MyBookmark");
```

## Step 3: Access the column content

We go through all the bookmarks in the document and display their names. If a bookmark is a column, we access the contents of that column using the column index and the `GetText` method:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Example source code for Bookmark Table Columns using Aspose.Words for .NET

Here is the full sample source code to demonstrate creating a bookmark on a table column using Aspose.Words for .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Bookmark Table Columns function of Aspose.Words for .NET. We followed a step-by-step guide to bookmark a specific column of a table in a Word document and jump to the contents of that column.
