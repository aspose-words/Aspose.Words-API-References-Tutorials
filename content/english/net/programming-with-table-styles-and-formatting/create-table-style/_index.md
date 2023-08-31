---
title: Create Table Style
linktitle: Create Table Style
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to creating a custom table style using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/create-table-style/
---

In this tutorial, we'll walk you through the step-by-step process to create a table style using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to create a custom style for your tables in your Word documents using Aspose.Words for .NET.

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
To start creating the table, we use the `StartTable()` method of the document builder, then we add cells to the table using the `InsertCell()` method and we write the contents of the cells to the using the `Write()` method.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Step 4: Create a table style
Now we can create a table style using the `TableStyle` class and the `Add()` method from the document`s `Styles` collection. We define the properties of the style, such as borders, margins and paddings.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Step 5: Apply the table style to the table
Finally, we apply the table style we created to the table using the `Style` property of the table.

```csharp
table.Style = tableStyle;
```

## Step 6: Save the modified document
Finally save the modified document to a file. You can choose an appropriate name and location for the output document.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Congratulation ! You have now created a custom style for your table using Aspose.Words for .NET.

### Sample source code for Create Table Style using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Conclusion
In this tutorial, we learned how to create a table style using Aspose.Words for .NET. By following this step-by-step guide, you can easily customize the style of your tables in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can improve the visual presentation of your Word documents and meet specific needs.