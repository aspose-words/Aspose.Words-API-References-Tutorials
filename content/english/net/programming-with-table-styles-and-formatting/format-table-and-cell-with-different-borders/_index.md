---
title: Format Table And Cell With Different Borders
linktitle: Format Table And Cell With Different Borders
second_title: Aspose.Words Document Processing API
description: Step by step guide to format table and cell with different borders using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

In this tutorial, we'll walk you through the step-by-step process to format a table and a cell with different borders using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to apply custom borders to specific table and cells in your Word documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited Word document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Create a new document and document builder
Next, you need to create a new instance of the `Document` class and a document constructor for that document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Start a new table and add cells
To start creating the table, we use the `StartTable()` method of the document builder, then we add cells to the table using the `InsertCell()` method and we write the contents of the cells to the using the `Writeln()` method.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
// Set borders for the whole table.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Set padding for this cell.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Specify a different cell padding for the second cell.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Clear cell formatting from previous operations.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Create thicker borders for the first cell in this row. It will be different
// relative to the borders defined for the table.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Step 4: Save the document

  amended
Finally save the modified document to a file. You can choose an appropriate name and location for the output document.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Congratulation ! You have now formatted a table and a cell with different borders using Aspose.Words for .NET.

### Sample source code for Format Table And Cell With Different Borders using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
// Set the borders for the entire table.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Set the cell shading for this cell.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Specify a different cell shading for the second cell.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Clear the cell formatting from previous operations.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Create larger borders for the first cell of this row. This will be different
// compared to the borders set for the table.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusion
In this tutorial, we learned how to format a table and a cell with different borders using Aspose.Words for .NET. By following this step-by-step guide, you can easily customize your table and cell borders in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can improve the visual presentation of your Word documents and meet specific needs.
