---
title: Floating Table Position
linktitle: Floating Table Position
second_title: Aspose.Words Document Processing API
description: Learn how to position a table in a floating position in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/floating-table-position/
---

In this tutorial, we are going to learn how to use Aspose.Words for .NET to position a table in a floating position in a Word document. We will follow a step by step guide to understand the code and implement this feature. At the end of this tutorial, you will be able to control the position and alignment of floating tables in your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Loading the document and accessing the table
To start Words Processing with the table, we need to load the document that contains it and access it. Follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Access to the array
Table table = doc.FirstSection.Body.Tables[0];
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory. Also, make sure the document contains a table that will be positioned in a floating position.

## Step 3: Positioning the floating board
Next, we'll position the table in a floating position using the properties provided by Aspose.Words for .NET. Use the following code:

```csharp
// Positioning the floating table
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

Here we use the `AbsoluteHorizontalDistance` property to set the absolute horizontal distance of the table from the left edge of the page. We also use the `RelativeVerticalAlignment` property to set the table's relative vertical alignment to the surrounding content.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the table positioned in a floating position. Use the following code:

```csharp
// Save the modified document
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Floating Table Position using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Conclusion
In this tutorial, we learned how to position a table in a floating position in a Word document using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can control the position and alignment of floating tables in your Word documents programmatically.
