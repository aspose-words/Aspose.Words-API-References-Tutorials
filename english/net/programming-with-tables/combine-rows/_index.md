---
title: Combine Rows
linktitle: Combine Rows
second_title: Aspose.Words Document Processing API
description: Learn how to combine table rows in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/combine-rows/
---

In this tutorial, we will learn how to use Aspose.Words for .NET to combine rows of tables in a Word document. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to manipulate and merge table rows in your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document and accessing the tables
To start Words Processing with tables, we need to load the document that contains them and access them. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Tables.docx");

// Access to tables
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Combining table rows
Next, we will combine the rows of the second table to the end of the first table. Use the following code:

```csharp
// Combination of table rows
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

Here we use a `while` loop to iterate over all the rows of the second array and add them to the end of the first array using the `Add` method. Next, we remove the second table from the document using the `Remove` method.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the combined table rows. Use the following code:

```csharp
// Save the modified document
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Combine Rows using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// The rows from the second table will be appended to the end of the first table.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Append all rows from the current table to the next tables
	// with different cell count and widths can be joined into one table.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Conclusion
In this tutorial, we learned how to combine rows of tables in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can manipulate table rows in your Word documents programmatically. This feature allows you to efficiently merge and organize your data into a table.
