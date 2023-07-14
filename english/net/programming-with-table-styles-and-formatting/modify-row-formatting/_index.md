---
title: Modify Row Formatting
linktitle: Modify Row Formatting
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to change table row formatting using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

In this tutorial, we'll walk you through the step-by-step process to change the formatting of a table row using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to change borders, height and line break of a table row in your Word documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is where your Word document is located. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load existing document
Next, you need to load the existing Word document into an instance of the `Document` class.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Step 3: Access the line to modify
To change the formatting of a table row, we need to navigate to the specific row in the table. We use the `GetChild()` and `FirstRow` methods to get the reference to the first row of the table.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Step 4: Change row formatting
Now we can change the row formatting using the properties of the `RowFormat` class. For example, we can remove line borders, set auto height and allow line break.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Sample source code for Modify Row Formatting using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Retrieve the first row in the table.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Conclusion
In this tutorial, we learned how to change the formatting of a table row using Aspose.Words for .NET. By following this step-by-step guide, you can easily adjust the borders, height, and line break of rows in your tables in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can customize the visual layout of your tables to your specific needs.
