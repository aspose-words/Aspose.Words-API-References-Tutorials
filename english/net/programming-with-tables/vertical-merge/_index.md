---
title: Vertical Merge
linktitle: Vertical Merge
second_title: Aspose.Words for .NET API Reference
description: Learn how to vertical merge cells in a table in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/vertical-merge/
---

In this tutorial, we will learn how to vertical merge cells in a table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to Vertical merge cells in your tables in Word documents.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document
To start working with the document, follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a new document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Merging Cells Vertical
Next we will merge the cells vertical in the table. Use the following code:

```csharp
// Insert a cell
builder. InsertCell();

// Apply the vertical merge to the first cell
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Insert another cell
builder. InsertCell();

// Apply no vertical merge to the cell
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Insert a cell
builder. InsertCell();

// Apply the vertical merge with the previous cell
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Insert another cell
builder. InsertCell();

// Apply no vertical merge to the cell
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

// End the creation of the table
builder. EndTable();
```

In this code, we use the DocumentBuilder constructor to insert cells into a table. We apply vertical merging to cells using the CellFormat.VerticalMerge property. We use CellMerge.First for the first cell merge, CellMerge.Previous to merge with the previous cell, and CellMerge.None for no vertical merge.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the merged cells. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Vertical Merge using Aspose.Words for .NET 
```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// This cell is vertical merged to the cell above and should be empty.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Conclusion
In this tutorial, we learned how to vertical merge cells in a table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can easily merge cells Vertical in your tables.
