---
title: Allow Cell Spacing
linktitle: Allow Cell Spacing
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to allow cell spacing using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/allow-cell-spacing/
---

In this tutorial, we will walk you through the step-by-step process of allowing cell spacing in tables using Aspose.Words for .NET. We will explain the C# source code that accomplishes this task and provide a comprehensive guide to help you understand and implement it in your own projects. By the end of this tutorial, you will have a clear understanding of how to manipulate table formatting in your Word documents using Aspose.Words for .NET.

## Step 1: Set the Document Directory
First, you need to set the path to your document directory. This is the location where your Word document is stored. Replace "YOUR DOCUMENT DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document
Next, you need to load the Word document into an instance of the `Document` class.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Step 3: Access the Table
To allow cell spacing, we need to access the table within the document. The `Table` class represents a table in Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Step 4: Enable Cell Spacing
Now, we can enable cell spacing by setting the `AllowCellSpacing` property of the table to `true`. This property determines whether the table can have cell spacing.

```csharp
table.AllowCellSpacing = true;
```

## Step 5: Set Cell Spacing
To specify the amount of space between cells, we use the `CellSpacing` property of the table. In this example, we set the cell spacing to 2 points.

```csharp
table. CellSpacing = 2;
```

## Step 6: Save the Modified Document
Finally, we save the modified document to a file. You can choose a suitable name and location for the output document.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.AllowCellSpacing.docx");
```

Congratulations! You have successfully allowed cell spacing in tables using Aspose.Words for .NET.

### Sample source code for Allow Cell Spacing using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AllowCellSpacing = true;
	table.CellSpacing = 2;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.AllowCellSpacing.docx");
```

## Conclusion
In this tutorial, we learned how to enable cell spacing in tables using Aspose.Words for .NET. By following the step-by-step guide, you can easily incorporate this functionality into your C# projects. Manipulating table formatting is an essential aspect of document processing, and Aspose. Words provides a powerful and flexible API to achieve this. With this knowledge, you can enhance the visual presentation of your Word documents and meet specific formatting requirements.
