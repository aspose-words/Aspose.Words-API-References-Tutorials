---
title: Expand Formatting On Cells And Row From Style
linktitle: Expand Formatting On Cells And Row From Style
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to expand formatting to cells and rows from a table style using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

In this tutorial, we'll walk you through the step-by-step process to expand formatting to cells and rows from a style using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to apply table style formatting to specific cells and rows in your Word documents using Aspose.Words for .NET.


## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is where your Word document is located. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load existing document
Next, you need to load the existing Word document into an instance of the `Document` class.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Step 3: Go to the first cell of the first table
To start, we need to navigate to the first cell of the first table in the document. We use the `GetChild()` and `FirstRow.FirstCell` methods to get the reference to the first cell.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Step 4: Show Initial Cell Formatting
Before Expanding the styles of the table, we display the current background color of the cell. This should be empty because the current formatting is stored in the style of the table.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Step 5: Expand Table Styles to Direct Formatting
Now we expand the table styles to direct formatting using the document's `ExpandTableStylesToDirectFormatting()` method.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Step 6: Show cell formatting after style expansion
Now we display the background color of the cell after Expanding the table styles. A blue background color should be applied from the table style.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Sample source code for Expand Formatting On Cells And Row From Style using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Get the first cell of the first table in the document.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// First print the color of the cell shading.
	// This should be empty as the current shading is stored in the table style.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Now print the cell shading after expanding table styles.
	// A blue background pattern color should have been applied from the table style.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Conclusion
In this tutorial, we learned how to expand formatting to cells and rows from a table style using Aspose.Words for .NET. By following this step-by-step guide, you can easily apply table style formatting to specific cells and rows in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can further customize the layout and presentation of your Word documents.
