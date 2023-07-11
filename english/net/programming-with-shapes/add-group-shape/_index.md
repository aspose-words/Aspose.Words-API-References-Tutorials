---
title: Add Group Shape
linktitle: Add Group Shape
second_title: Aspose.Words Document Processing API
description: Learn how to add a group shape with multiple shapes to a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-shapes/add-group-shape/
---

This tutorial explains how to add a group shape containing multiple shapes to a Word document using Aspose.Words for .NET. Group shapes allow you to combine and manipulate multiple shapes as a single entity.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where you want to save the document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a New Document and GroupShape
Create a new instance of the `Document` class and `GroupShape` object to work with the document.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Step 3: Create and Add Shapes to the GroupShape
Create individual shapes such as `accentBorderShape` and `actionButtonShape` using the `Shape` class. Customize their properties as desired. Append these shapes to the `groupShape` object.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Step 4: Set Dimensions for the GroupShape
Set the width, height, and coordinate size for the `groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Step 5: Insert the GroupShape into the Document
Create a `DocumentBuilder` object and insert the `groupShape` into the document using the `InsertNode` method.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Step 6: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Example source code for Add Group Shape using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

That's it! You have successfully added a group shape containing multiple shapes to your Word document using Aspose.W
