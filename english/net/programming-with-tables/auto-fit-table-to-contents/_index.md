---
title: Auto Fit Table To Contents
linktitle: Auto Fit Table To Contents
second_title: Aspose.Words Document Processing API
description: Learn how to auto fit a table to its contents in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/auto-fit-table-to-contents/
---

In this tutorial, we will learn how to use Aspose.Words for .NET to auto fit a table to its contents in a Word document using C#. We will go through the step-by-step process of writing code to achieve this functionality. By the end of this tutorial, you will have a clear understanding of how to manipulate tables in Word documents programmatically.

## Step 1: Set up the project
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Load the Word document
To start working with the table, we need to load the Word document that contains the table. Follow these steps:

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load the Word document
Document doc = new Document(dataDir + "Tables.docx");
```

Make sure to replace "YOUR DOCUMENT DIRECTORY" with the actual path to your document.

## Step 3: Access the table and auto-fit it to contents
Next, we need to access the table within the document and apply the auto-fit behavior. Use the following code:

```csharp
// Access the table
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Auto-fit the table to its contents
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

Here, we are casting the first child node of type `Table` from the document and then using the `AutoFit` method with the `AutoFitToContents` behavior to adjust the table width to fit its content.

## Step 4: Save the modified document
Finally, we need to save the modified document with the auto-fitted table. Use the following code:

```csharp
// Save the modified document
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Ensure that you specify the correct path and file name for the output document.

### Sample source code for Auto Fit Table To Contents using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Conclusion
In this tutorial, we have learned how to auto fit a table to its contents in a Word document using Aspose.Words for .NET. By following the step-by-step guide and implementing the provided C# code, you can manipulate tables in your Word documents programmatically. This allows you to dynamically adjust the table width based on its content, providing a more professional and visually appealing document.