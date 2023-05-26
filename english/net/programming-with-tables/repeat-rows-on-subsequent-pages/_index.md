---
title: Repeat Rows On Subsequent Pages
linktitle: Repeat Rows On Subsequent Pages
second_title: Aspose.Words for .NET API Reference
description: Learn how to repeat table rows on subsequent pages in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

In this tutorial, we will learn how to repeat the rows of a table on subsequent pages of a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to specify rows to repeat on subsequent pages of your table in your Word documents.

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

## Step 3: Building the table with repeated rows
Next, we'll build a table with repeated rows on subsequent pages. Use the following code:

```csharp
// Beginning of the table
builder. StartTable();

// Configuration of the first line parameters (header lines)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Insert the first cell of the first row
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Insert the second cell of the first row
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Configure the parameters of the following lines
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Loop to insert the cells in the following rows
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// End of table
builder. EndTable();
```

Here we use the document builder to build a table with two header rows and multiple data rows. The `RowFormat.HeadingFormat` parameters are used to mark header rows that should be repeated on subsequent pages.

## Step 4: Saving the modified document
Finally U.S

  need to save the modified document with the header rows repeated on subsequent pages of the table. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Repeat Rows On Subsequent Pages using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Conclusion
In this tutorial, we learned how to repeat the rows of a table on subsequent pages of a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can specify which lines to repeat according to your specific needs in your Word documents.
