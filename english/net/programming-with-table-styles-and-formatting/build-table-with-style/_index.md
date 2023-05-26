---
title: Build Table With Style
linktitle: Build Table With Style
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to building a table with a custom style using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/build-table-with-style/
---

In this tutorial, we'll walk you through the step-by-step process to build a styled table using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to create a table with a custom style in your Word documents using Aspose.Words for .NET.

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

## Step 3: Start a new table and insert a cell
To start building the table, we use the `StartTable()` method of the document builder, then we insert a cell into the table using the `InsertCell()` method.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Step 4: Define the style of the table
Now we can set the table style using the `StyleIdentifier` property. In this example, we are using the "MediumShading1Accent1" style.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Step 5: Apply style options to the table
We can specify which characteristics should be formatted by the style using the `StyleOptions` property of the array. In this example, we apply the following options: "FirstColumn", "RowBands" and "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Step 6: Automatically adjust table size
To automatically adjust the size of the array based on its contents, we use the `AutoFit()` method with the `AutoFitBehavior.AutoFitToContents` behavior.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Step 7: Add content to cells
Now we can add content to cells using the `Writeln()` and `InsertCell()` methods of the document builder. In this example, we add the headers for the "Item" and "Quantity (

kg)" and the corresponding data.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Step 8: Save the modified document
Finally, we save the modified document to a file. You can choose an appropriate name and location for the output document.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Congratulation ! You have now built a custom styled table using Aspose.Words for .NET.

### Sample source code for Build Table With Style using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// We must insert at least one row first before setting any table formatting.
	builder.InsertCell();
	// Set the table style used based on the unique style identifier.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Apply which features should be formatted by the style.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Conclusion
In this tutorial, we learned how to build a styled table using Aspose.Words for .NET. By following this step-by-step guide, you can easily customize the style of your tables in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can improve the visual presentation of your Word documents and meet specific needs.
