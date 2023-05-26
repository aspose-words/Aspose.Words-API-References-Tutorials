---
title: Auto Fit To Page Width
linktitle: Auto Fit To Page Width
second_title: Aspose.Words for .NET API Reference
description: Learn how to auto fit a table to page width in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/auto-fit-to-page-width/
---

In this tutorial, we will learn how to use Aspose.Words for .NET to auto fit a table to page width in a Word document. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to manipulate tables in Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Creating and Configuring the Document
To start working with the table, we need to create a document and configure the document generator. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and the document generator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Inserting and Configuring the Table
Next, we'll insert a table into the document with a width that takes up half the width of the page. Use the following code:

```csharp
// Insert the table and configure its width
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Here we use the document builder to start creating the table, insert cells, and set the preferred width of the table to 50% of the page width. Then we add text in each cell.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the table adjusted to the width of the page. Use the following code:

```csharp
// Save the modified document
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Be sure to specify the correct path and filename for the output document.
  
### Sample source code for Auto Fit To Page Width using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insert a table with a width that takes up half the page width.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Conclusion
In this tutorial, we learned how to auto fit a table to page width in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can manipulate tables in your Word documents programmatically. This feature allows you to dynamically adapt the width of the table according to the page, thus offering a professional and visually appealing document.
