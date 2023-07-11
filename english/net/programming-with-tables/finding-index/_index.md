---
title: Finding Index
linktitle: Finding Index
second_title: Aspose.Words Document Processing API
description: Learn how to find table, row and cell indexes in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/finding-index/
---

In this tutorial, we will learn how to use Aspose.Words for .NET to find the indexes of a table, row and cell in a Word document. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to find the indexes of array elements in your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document and accessing the table
To start working with the table, we need to load the document that contains it and access it. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Tables.docx");

// Access to the array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Find Table, Row and Cell Index
Next, we'll find the table, row, and cell indexes in the array using the methods provided by Aspose.Words for .NET. Use the following code:

```csharp
// Find the table index
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
int tableIndex = allTables.IndexOf(table);
Console.WriteLine("\nTable index is " + tableIndex);

// Find the row index
int rowIndex = table.IndexOf(table.LastRow);
Console.WriteLine("\nLine index is " + rowIndex);

// Find the cell index
Row row = table. LastRow;
int cellIndex = row.IndexOf(row.Cells[4]);
Console.WriteLine("\nCell index is " + cellIndex);
```

Here we use the `GetChildNodes` method to get all the tables in the document. Then we use `IndexOf` to find the index of the specific table in the collection of all tables. Similarly, we use `IndexOf` to find the index of the last row in the table, and `IndexOf` inside a row to find the index of a specific cell.

### Sample source code for Finding Index using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
	int tableIndex = allTables.IndexOf(table);
	Console.WriteLine("\nTable index is " + tableIndex);
	int rowIndex = table.IndexOf(table.LastRow);
	Console.WriteLine("\nRow index is " + rowIndex);
	Row row = table.LastRow;
	int cellIndex = row.IndexOf(row.Cells[4]);
	Console.WriteLine("\nCell index is " + cellIndex);
```

## Conclusion
In this tutorial, we learned how to find the indexes of a table, row and cell in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can find and identify the exact positions of array elements in your Word documents programmatically. This feature allows you to precisely manipulate and interact with array elements to suit your specific needs.
