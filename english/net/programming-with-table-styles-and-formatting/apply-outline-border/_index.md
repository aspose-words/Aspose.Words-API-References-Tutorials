---
title: Apply Outline Border
linktitle: Apply Outline Border
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to applying an outline border to a table using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-styles-and-formatting/apply-outline-border/
---

In this tutorial, we'll walk you through the step-by-step process to apply an outline border to a table using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. By the end of this tutorial, you will have a clear understanding of how to manipulate table borders in your Word documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is where your Word document is stored. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Upload the document
Next, you need to load the Word document into an instance of the `Document` class.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Step 3: Access the table
To apply an outline border, we need to access the table in the document. The `Table` class represents a table in Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Step 4: Align the table to the center of the page
Now we can align the table to the center of the page using the `Alignment` property of the table.

```csharp
table. Alignment = Table Alignment. Center;
```

## Step 5: Erase existing table borders
To start with a new outline border, we first need to erase all existing borders from the table. This can be done using the `ClearBorders()` method.

```csharp
table. ClearBorders();
```

## Step 6: Define a green border around the table
We can now set a green border around the table using the `SetBorder()` method for each side of the table. In this example, we are using a "Single" type border with a thickness of 1.5 points and a green color.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Step 7: Fill the cells with a background color
To improve the visual presentation of the table, we can fill the cells with a ground background color

idea. In this example, we are using a light green color.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Step 8: Save the modified document
Finally, we save the modified document to a file. You can choose an appropriate name and location for the output document.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Congratulation ! You have now applied an outline border to a table using Aspose.Words for .NET.

### Sample source code for Apply Outline Border using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Align the table to the center of the page.
	table.Alignment = TableAlignment.Center;
	// Clear any existing borders from the table.
	table.ClearBorders();
	// Set a green border around the table but not inside.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Fill the cells with a light green solid color.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Conclusion
In this tutorial, we learned how to apply an outline border to a table using Aspose.Words for .NET. By following this step-by-step guide, you can easily integrate this functionality into your C# projects. Manipulating table formatting is an essential aspect of document processing, and Aspose.Words offers a powerful and flexible API to achieve this. With this knowledge, you can improve the visual presentation of your Word documents and meet specific requirements.
