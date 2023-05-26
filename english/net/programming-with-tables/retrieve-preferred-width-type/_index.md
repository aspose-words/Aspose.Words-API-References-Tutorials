---
title: Retrieve Preferred Width Type
linktitle: Retrieve Preferred Width Type
second_title: Aspose.Words for .NET API Reference
description: Learn how to retrieve the type and preferred width value of a cell in a Word table with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/retrieve-preferred-width-type/
---

In this tutorial, we will learn how to retrieve the preferred width type and its value from a table cell in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to retrieve the preferred width type (absolute, relative, or automatic) and its value for a specific cell in your Word document tables.

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

## Step 3: Retrieving the preferred width type and value
Next, we'll retrieve the preferred width type and its value for a specific table cell. Use the following code:

```csharp
// Retrieve the table
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Activate automatic table adjustment
table. AllowAutoFit = true;

// Retrieve the first cell of the first row
Cell firstCell = table.FirstRow.FirstCell;

// Retrieve the preferred width type and its value
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Here we use the document to fetch the first table, then we enable automatic table fit with the `AllowAutoFit` property. Then we retrieve the first cell of the first row of the table. From this cell, we can retrieve the preferred width type with the `PreferredWidth.Type` property and its value with the `PreferredWidth.Value` property.

### Sample source code for Retrieve Preferred Width Type using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Conclusion
In this tutorial, we learned how to retrieve the preferred width type and its value from a table cell in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can retrieve this information for specific cells in your Word document tables.
