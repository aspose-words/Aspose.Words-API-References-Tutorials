---
title: Apply Row Formatting
linktitle: Apply Row Formatting
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to apply row formatting to a table using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

In this tutorial, we'll walk you through the step-by-step process to apply row formatting to a table using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. By the end of this tutorial, you will have a clear understanding of how to format table rows in your Word documents using Aspose.Words for .NET.

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

## Step 3: Start a new board
To apply row formatting, we must first start a new table using the `StartTable()` method of the document constructor.

```csharp
Table table = builder. StartTable();
```

## Step 4: Insert cell and go to row format
Now we can insert a cell into the table and access the row format for that cell using the document builder's `InsertCell()` and `RowFormat` methods.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Step 5: Set Row Height
To set the row height, we use the `Height` and `HeightRule` properties of the row format. In this example, we set a row height of 100 points and use the `Exactly` rule.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Step 6: Define table formatting
Some formatting properties can be set on the table itself and are applied to all table rows. In this example, we set the table margin properties using the `LeftPadding`, `RightPadding`, `TopPadding` and `BottomPadding` properties.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Step 7: Add content to the row
Now we can

We're going to add content to the line using the methods of the document constructor. In this example, we use the `Writeln()` method to add text to the line.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Step 8: Finish the line and the table
Once we have added the content to the row, we can end the row using the `EndRow()` method and then end the table using the `EndTable()` method.

```csharp
builder. EndRow();
builder. EndTable();
```

## Step 9: Save the modified document
Finally, we save the modified document to a file. You can choose an appropriate name and location for the output document.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Congratulation ! You have now applied row formatting to a table using Aspose.Words for .NET.

### Sample source code for Apply Row Formatting using Aspose.Words for .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Conclusion
In this tutorial, we learned how to apply row formatting to a table using Aspose.Words for .NET. By following this step-by-step guide, you can easily integrate this functionality into your C# projects. Manipulating table row formatting is an essential aspect of document processing, and Aspose.Words offers a powerful and flexible API to achieve this. With this knowledge, you can improve the visual presentation of your Word documents and meet specific requirements.
