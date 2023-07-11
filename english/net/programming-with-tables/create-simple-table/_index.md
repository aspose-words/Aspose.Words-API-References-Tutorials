---
title: Create Simple Table
linktitle: Create Simple Table
second_title: Aspose.Words Document Processing API
description: Learn how to create a simple table in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/create-simple-table/
---

In this tutorial, we are going to learn how to create a simple table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to create custom tables in your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Creating the document and initializing the document generator
To start building the table, we need to create a new document and initialize the document builder. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and initialize the document generator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Building the array
Next, we'll build the table using the methods provided by the document builder. Use the following code:

```csharp
// Begin array construction
builder. StartTable();

// Construction of the first cell of the first row
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Construction of the second cell of the first row
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

// Call the following method to end the first line and start a new line
builder. EndRow();

// Construction of the first cell of the second row
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Construction of the second cell of the second row
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Call the next method to end the second line
builder. EndRow();

// Indication that the construction of the table is finished
builder. EndTable();
```

Here we use the document builder to build the table step by step. We start by calling `StartTable()` to initialize the table, then use `InsertCell()` to insert cells and `Write()` to add content to each cell. We also use `EndRow()` to end a row and start a new row. Finally, we call `EndTable()` to indicate that the table construction is complete.

## Step 4: Save the document
Finally, we need to save

  the document with the created table. Use the following code:

```csharp
// Save the document
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Create Simple Table using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Start building the table.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Build the second cell.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Call the following method to end the row and start a new row.
	builder.EndRow();
	// Build the first cell of the second row.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Build the second cell.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	// Signal that we have finished building the table.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Conclusion
In this tutorial, we learned how to create a simple table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can create custom tables in your Word documents programmatically. This feature allows you to format and organize your data in a structured and clear way.
