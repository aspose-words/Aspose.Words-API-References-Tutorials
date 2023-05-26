---
title: Set Table Row Formatting
linktitle: Set Table Row Formatting
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to setting table row formatting using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

In this tutorial, we'll walk you through the step-by-step process to set table row formatting using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to adjust the height and paddings of a table row in your Word documents using Aspose.Words for .NET.

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
Table table = builder. StartTable();
builder. InsertCell();
```

## Step 4: Define the line formatting
Now we can set the row formatting by accessing the `RowFormat` object of the `DocumentBuilder` object. We can set the line height and the margins (paddings) using the corresponding properties.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Step 5: Set table margins
Next, we can set the table paddings by accessing the corresponding properties of the `Table` object. These margins will be applied to all rows of the table.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Step 6: Add content to the row
Finally, we can add content to the line using the document builder's `Writeln()` method.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Step 7: Finish the table and save the document
In

end, we finish creating the table using the `EndRow()` and `EndTable()` method, then we save the modified document to a file.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Sample source code for Set Table Row Formatting using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// These formatting properties are set on the table and are applied to all rows in the table.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Conclusion
In this tutorial, we learned how to set table row formatting using Aspose.Words for .NET. By following this step-by-step guide, you can easily adjust table row height and margins in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can customize the visual layout of your tables to your specific needs.
