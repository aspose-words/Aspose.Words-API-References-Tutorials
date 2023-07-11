---
title: Clone Complete Table
linktitle: Clone Complete Table
second_title: Aspose.Words Document Processing API
description: Learn how to clone an entire table into a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/clone-complete-table/
---

In this tutorial, we will learn how to use Aspose.Words for .NET to clone an entire table into a Word document. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to clone tables into your Word documents programmatically.

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

## Step 3: Full Array Clone
Next, we'll clone the entire table and insert it into the document after the original. Use the following code:

```csharp
// Clone the array
Table tableClone = (Table)table.Clone(true);

// Insert the cloned table into the document after the original
table.ParentNode.InsertAfter(tableClone, table);

// Insert an empty paragraph between the two tables
// Otherwise they will be combined into one on save (this is due to document validation)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

Here we are using the `Clone` method to create a complete copy of the array. Then we use `InsertAfter` to insert the cloned table into the document, after the original table. We also add an empty paragraph between the two tables to prevent them from being merged when saving.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the cloned table. Use the following code:

```csharp
// Save the modified document
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Be sure to specify the correct path and filename for the output document.
  
### Sample source code for Clone Complete Table using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Clone the table and insert it into the document after the original.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Insert an empty paragraph between the two tables,
	// or else they will be combined into one upon saving this has to do with document validation.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusion
In this tutorial, we learned how to clone an entire table into a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can clone tables in your Word documents programmatically. This feature allows you to perform advanced manipulations on arrays to suit your specific needs.
