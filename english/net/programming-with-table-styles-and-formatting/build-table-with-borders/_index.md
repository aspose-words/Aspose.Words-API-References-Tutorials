---
title: Build Table With Borders
linktitle: Build Table With Borders
second_title: Aspose.Words Document Processing API
description: Step by step guide to building a table with borders using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

In this tutorial, we'll walk you through the step-by-step process to build a table with borders using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to create a table with custom borders in your Word documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is where your Word document is stored. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load existing document
Next, you need to load the existing Word document into an instance of the `Document` class.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Step 3: Access the table and remove existing borders
To start building the table with borders, we need to navigate to the table in the document and remove the existing borders. The `ClearBorders()` method removes all borders from the table.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## Step 4: Set Table Borders
Now we can set the table borders using the `SetBorders()` method. In this example, we are using a green colored border with a thickness of 1.5 points.

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## Step 5: Save the modified document
Finally, we save the modified document to a file. You can choose an appropriate name and location for the output document.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

Congratulation ! You have now built a table with custom borders using Aspose.Words for .NET.

### Sample source code for Build Table With Borders using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Clear any existing borders from the table.
	table.ClearBorders();
	// Set a green border around and inside the table.
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## Conclusion
In this tutorial, we learned how to build a table with borders using Aspose.Words for .NET. By following this step-by-step guide, you can easily customize your table borders in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can improve the visual presentation of your Word documents and meet specific needs.
