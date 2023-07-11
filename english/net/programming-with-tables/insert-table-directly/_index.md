---
title: Insert Table Directly
linktitle: Insert Table Directly
second_title: Aspose.Words Document Processing API
description: Learn how to insert a table directly into a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/insert-table-directly/
---

In this tutorial, we will learn how to directly insert a table into a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to insert tables directly into your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Creating the Document and Table
To start working with the array, we need to create a new document and initialize the array. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation
Document doc = new Document();

// Create the array
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Building the array
Next, we'll build the table by adding rows and cells. Use the following code as an example:

```csharp
// Create the first row
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Create the first cell
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplicate the cell for the second cell in the row
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

Here we create a row with the `AllowBreakAcrossPages` property set to `true` to allow page breaking between rows. We then create a cell with a colored background, fixed width, and specified text content. We then duplicate this cell to create the second cell in the row.

## Step 4: Auto Fit Table
We can apply automatic adjustments to the table to format it correctly. Use the following code:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

This line of code applies an auto-fit based on fixed column widths.

## Step 5: Registering the

  modified document
Finally, we need to save the modified document with the table inserted directly. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Insert Table Directly using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// We start by creating the table object. Note that we must pass the document object
	// to the constructor of each node. This is because every node we create must belong
	// to some document.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Here we could call EnsureMinimum to create the rows and cells for us. This method is used
	// to ensure that the specified node is valid. In this case, a valid table should have at least one Row and one cell.
	// Instead, we will handle creating the row and table ourselves.
	// This would be the best way to do this if we were creating a table inside an algorithm.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// We can now apply any auto fit settings.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// We would then repeat the process for the other cells and rows in the table.
	// We can also speed things up by cloning existing cells and rows.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Conclusion
In this tutorial, we learned how to directly insert a table into a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can insert tables directly into your Word documents programmatically. This feature allows you to create and customize tables according to your specific needs.
