---
title: Convert To Horizontally Merged Cells
linktitle: Convert To Horizontally Merged Cells
second_title: Aspose.Words Document Processing API
description: Learn how to convert table cells to horizontally merged cells in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/convert-to-horizontally-merged-cells/
---

In this tutorial, we will learn how to use Aspose.Words for .NET to convert table cells to horizontally merged cells in a Word document. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to manipulate table cells in your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document and accessing the table
To start working with the table, we need to load the document that contains it and access it. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Access to the array
Table table = doc.FirstSection.Body.Tables[0];
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory. Also, make sure the document contains a table with horizontally merged cells.

## Step 3: Convert to horizontally merged cells
Next, we will convert the table cells to horizontally merged cells using the `ConvertToHorizontallyMergedCells()` method. Use the following code:

```csharp
// Convert to horizontally merged cells
table. ConvertToHorizontallyMergedCells();
```

Here we just call the `ConvertToHorizontallyMergedCells()` method on the array to perform the conversion.

### Sample source code for Convert To Horizontally Merged Cells using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Now merged cells have appropriate merge flags.
	table.ConvertToHorizontallyMergedCells();
```

## Conclusion
In this tutorial, we learned how to convert table cells to horizontally merged cells in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can manipulate table cells in your Word documents programmatically. This feature allows you to manage and organize your data in a flexible and personalized way in a table.
