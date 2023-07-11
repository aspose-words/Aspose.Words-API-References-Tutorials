---
title: Keep Table Together
linktitle: Keep Table Together
second_title: Aspose.Words Document Processing API
description: Learn how to hold a table together in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/keep-table-together/
---

In this tutorial, we are going to learn how to hold a table together in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to keep a table intact without it splitting across multiple pages in your Word documents.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document and retrieving the table
To start working with the table, we need to load the document and fetch the table we want to keep together. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Retrieve the table
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Enable "KeepWithNext" option
To keep the table together and prevent it from splitting across multiple pages, we need to enable the "KeepWithNext" option for each paragraph in the table except for the last paragraphs of the last row of the table. Use the following code:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Here we loop through each cell in the table and enable the "KeepWithNext" option for each paragraph in the cell except for the last paragraphs of the last row in the table.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the table held together. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Keep Table Together using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// We need to enable KeepWithNext for every paragraph in the table to keep it from breaking across a page,
	// except for the last paragraphs in the last row of the table.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusion
In this tutorial, we learned how to hold a table together in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can keep a table intact and prevent it from splitting across multiple pages in your documents. This feature gives you more control over the appearance and layout of your tables in your documents.
