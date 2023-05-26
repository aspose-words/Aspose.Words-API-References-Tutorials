---
title: Get Distance Between Table Surrounding Text
linktitle: Get Distance Between Table Surrounding Text
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to get the distance between text and a table in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

In this tutorial, we'll walk you through the step-by-step process to get the distance between surrounding text in a table using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to access the various distances between a table and the surrounding text in your Word documents using Aspose.Words for .NET.

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

## Step 3: Get the distance between the table and the surrounding text
To get the distance between the table and the surrounding text, we need to access the table in the document using the `GetChild()` method and the `NodeType.Table` property. We can then display the different distances using the array properties `DistanceTop`, `DistanceBottom`, `DistanceRight` and `DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Sample source code for Get Distance Between Table Surrounding Text using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Conclusion
In this tutorial, we learned how to get the distance between surrounding text in a table using Aspose.Words for .NET. By following this step-by-step guide, you can easily access the various distances between a table and the surrounding text in your Word documents. Aspose.Words offers a powerful and flexible API for manipulating and formatting tables in your documents. With this knowledge, you can analyze the layout of your tables in relation to the text and meet specific needs.
