---
title: Split Table
linktitle: Split Table
second_title: Aspose.Words Document Processing API
description: Learn how to split a table in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/split-table/
---

In this tutorial, we are going to learn how to split a table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to split a table from a certain row in your Word documents.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document
To start working with the document, follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Tables.docx");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory and provide the correct file name.

## Step 3: Dividing the table
Next we will split the table from a certain row. Use the following code:

```csharp
// Retrieve the first table
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Determination of the line from which to divide the table
Row row = firstTable.Rows[2];

// Create a new container for the split table
Table table = (Table)firstTable.Clone(false);

// Insert the container after the original table
firstTable.ParentNode.InsertAfter(table, firstTable);

// Add a buffer paragraph to maintain a distance between tables
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Move rows from the original table to the split table
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Here we use the document to retrieve the first table from the document node. Then we determine the row from which we want to split the table, in this example it is the third row (index 2). We then create a new container by cloning the original table and then insert it after the original table. We also add a buffer paragraph to maintain a distance between the two tables. Then we move rows from the original table to the split table using a do-while loop until we reach the specified row.

## Step 4: Saving the modified document
Finally, we need to save the

  document modified with the split table. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Split Table using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// We will split the table at the third row (inclusive).
Row row = firstTable.Rows[2];
// Create a new container for the split table.
Table table = (Table) firstTable.Clone(false);
// Insert the container after the original.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Add a buffer paragraph to ensure the tables stay apart.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Conclusion
In this tutorial, we learned how to split a table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can easily split tables from a certain line in your Word documents.
