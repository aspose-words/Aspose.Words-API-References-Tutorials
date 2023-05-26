---
title: Get Table Position
linktitle: Get Table Position
second_title: Aspose.Words for .NET API Reference
description: Learn how to get the position of a table in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/get-table-position/
---

In this tutorial, we are going to learn how to get the position of a table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to get table positioning properties in your Word documents programmatically.

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

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory. Also, make sure the document contains the table whose position you want to get.

## Step 3: Getting Array Positioning Properties
Next, we'll check the positioning type of the array and get the appropriate positioning properties. Use the following code:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

Here we use a condition to check if the array is of float type. If so, we print the `RelativeHorizontalAlignment` and `RelativeVerticalAlignment` properties to get the relative horizontal and vertical alignment of the table. Otherwise, we print the `Alignment` property to get the array alignment.

### Sample source code for Get Table Position using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Conclusion
In this tutorial, we learned how to get the position of a table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can get table positioning properties in your Word documents programmatically. This feature allows you to analyze and manipulate arrays according to their specific positions.
