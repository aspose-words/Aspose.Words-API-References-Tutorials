---
title: Horizontal Merge
linktitle: Horizontal Merge
second_title: Aspose.Words for .NET API Reference
description: Learn how to horizontally merge cells in a Word table with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/horizontal-merge/
---

In this tutorial, we will learn how to horizontally merge cells in a table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to merge cells horizontally in your Word tables programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Creating the document and initializing the document generator
To start working with the table and cells, we need to create a new document and initialize the document generator. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and initialize the document generator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Building the table with horizontal merging of cells
Next, we'll build the table and apply horizontal cell merging using the properties provided by Aspose.Words for .NET. Use the following code:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// This cell is merged with the previous one and should be empty.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

Here we use the document builder to build the table and set the cell horizontal merge properties. We use the `HorizontalMerge` property of the `CellFormat` object to specify the type of horizontal merge to apply to each cell. Using `CellMerge.First` we merge the first cell with the next one, while using `CellMerge.Previous` we merge the current cell with the previous cell. `CellMerge.None` indicates that the cell should not be merged.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the cells merged horizontally. Use the following code:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Horizontal Merge using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// This cell is merged to the previous and should be empty.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Conclusion
In this tutorial, we learned how to horizontally merge cells in a table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can apply horizontal cell merging in your Word tables programmatically. This feature allows you to create more complex table layouts and better organize your data.
