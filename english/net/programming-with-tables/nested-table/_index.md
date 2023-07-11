---
title: Nested Table
linktitle: Nested Table
second_title: Aspose.Words Document Processing API
description: Learn how to create a nested table in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/nested-table/
---

In this tutorial, we will learn how to create a nested table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to create nested tables in your Word documents programmatically.

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

## Step 3: Building the Nested Table
Next, we'll build the nested table by inserting cells into the outer table and creating a new table inside the first cell. Use the following code:

```csharp
// Insert the first cell of the outer table
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Insert the second cell of the outer table
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Termination of the outer table
builder. EndTable();

// Move to the first cell of the outer table
builder.MoveTo(cell.FirstParagraph);

// Build the inner table
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// End of the inner table
builder. EndTable();
```

Here we use the document builder to insert cells and content into the outer table. Then we move the document builder cursor to the first cell of the outer table and build a new table inside by inserting cells and content.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the nested table. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Be sure to specify the correct path and name file for the output document.

### Sample source code for Nested Table using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// This call is important to create a nested table within the first table. 
	// Without this call, the cells inserted below will be appended to the outer table.
	builder.EndTable();
	// Move to the first cell of the outer table.
	builder.MoveTo(cell.FirstParagraph);
	// Build the inner table.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Conclusion
In this tutorial, we learned how to create a nested table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can create nested tables according to your specific needs in your Word documents programmatically.

