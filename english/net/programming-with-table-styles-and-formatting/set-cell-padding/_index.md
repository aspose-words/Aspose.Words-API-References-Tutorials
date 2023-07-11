---
title: Set Cell Padding
linktitle: Set Cell Padding
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to setting table cell margins using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/set-cell-padding/
---

In this tutorial, we'll walk you through the step-by-step process to set table cell margins using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to adjust the left, top, right and bottom margins (space) of cell content in your tables in your Word documents using Aspose.Words for .NET .

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

## Step 3: Start a new table and add a cell
To start creating the table, we use the `StartTable()` method of the document constructor, then we add a cell to the table using the `InsertCell()` method.

```csharp
builder. StartTable();
builder. InsertCell();
```

## Step 4: Set cell margins
Now we can set the cell margins using the `SetPaddings()` method of the `CellFormat` object. Margins are defined in points and specified in the order left, top, right, and bottom.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Step 5: Add content to the cell
Then we can add content to the cell using the document builder's `Writeln()` method.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Step 6: Finish the table and save the document
Finally, we finish creating the table using the `EndRow()` method and `EndTable()`, then we save the modified document to a file.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Sample source code for Set Cell Padding using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Sets the amount of space (in points) to add to the left/top/right/bottom of the cell's contents.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Conclusion
In this tutorial, we learned how to set the margins of a table cell using Aspose.Words for .NET. By following this step-by-step guide, you can easily adjust cell margins to create spaces to the left, top, right, and bottom of content in your tables in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can customize the formatting of your tables to your specific needs.
