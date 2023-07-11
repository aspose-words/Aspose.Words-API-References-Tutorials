---
title: Row Format Disable Break Across Pages
linktitle: Row Format Disable Break Across Pages
second_title: Aspose.Words Document Processing API
description: Learn how to disable line break for a table across multiple pages in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/row-format-disable-break-across-pages/
---

In this tutorial, we are going to learn how to disable line break of a multi-page table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to disable line breaking for all rows in your table in your Word documents.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document
To start working with the document, follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory and provide the correct file name.

## Step 3: Disable table row break
Next, we will disable row breaking for all rows in the table. Use the following code:

```csharp
// Retrieve the table
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Disable row break for all rows in the table
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

Here we use the document to fetch the first table and then iterate through all the rows in the table using a foreach loop. Inside the loop, we disable row breaking for each row by setting the `RowFormat.AllowBreakAcrossPages` property to `false`.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the table line break disabled. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Row Format Disable Break Across Pages using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Disable breaking across pages for all rows in the table.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusion
In this tutorial, we learned how to disable line break of a multi-page table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can apply this disablement to your tables in your Word documents.
