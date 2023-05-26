---
title: Get Floating Table Position
linktitle: Get Floating Table Position
second_title: Aspose.Words for .NET API Reference
description: Learn how to get the position of floating tables in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/get-floating-table-position/
---

In this tutorial, we will learn how to get the position of a floating table in a Word document using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to get the positioning properties of a floating table in your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document and accessing the tables
To start working with tables, we need to load the document that contains them and access them. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory. Also, make sure the document contains floating tables.

## Step 3: Getting Floating Table Positioning Properties
Next, we'll loop through all the tables in the document and get the floating table positioning properties. Use the following code:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// If the array is a floating type, then print its positioning properties.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

Here we are using a `foreach` loop to loop through all the arrays in the document. We check if the array is float type by checking the `TextWrapping` property. If so, we print the table's positioning properties, such as horizontal anchor, vertical anchor, absolute horizontal and vertical distances, overlapping permission, absolute horizontal distance, and vertical alignment relative.
 
### Sample source code for Get Floating Table Position using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// If the table is floating type, then print its positioning properties.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Conclusion
In this tutorial, we learned how to get the position of a floating table in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can get the positioning properties of floating tables in your Word documents programmatically. This feature allows you to analyze and manipulate floating tables according to your specific needs.
