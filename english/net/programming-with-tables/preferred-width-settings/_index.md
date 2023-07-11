---
title: Preferred Width Settings
linktitle: Preferred Width Settings
second_title: Aspose.Words Document Processing API
description: Learn how to set preferred table cell widths in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/preferred-width-settings/
---

In this tutorial, we will learn how to set preferred width settings for table cells in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to specify different preferred widths for your table cells in your Word documents.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Creating the document and initializing the document generator
To start working with the document and document generator, follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation
Document doc = new Document();

// Initialize the document generator
DocumentBuilder builder = new DocumentBuilder(doc);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Building the table with preferred widths
Next, we'll build a table with three cells that have different preferred widths. Use the following code:

```csharp
// Beginning of the table
builder. StartTable();

// Insert a cell of absolute size
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Insert a cell of relative size (in percentage)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Insert an auto-sized cell
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// End of table
builder. EndTable();
```

Here we use the document builder to build a table with three cells. The first cell has a preferred width of 40 points, the second cell has a preferred width of 20% of the table width, and the third cell has an automatic preferred width that adjusts

  depending on the space available.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the preferred width settings defined for the table cells. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Preferred Width Settings using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insert a table row made up of three cells which have different preferred widths.
	builder.StartTable();
	// Insert an absolute sized cell.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Insert a relative (percent) sized cell.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Insert a auto sized cell.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Conclusion
In this tutorial, we learned how to set preferred width settings for table cells in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can customize your table cell widths to your specific needs in your Word documents.
