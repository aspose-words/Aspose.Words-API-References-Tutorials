---
title: Add Corners Snipped
linktitle: Add Corners Snipped
second_title: Aspose.Words for .NET API Reference
description: Learn how to add a shape with corners snipped to a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-shapes/add-corners-snipped/
---

This tutorial explains how to add a shape with corners snipped to a Word document using Aspose.Words for .NET. The corners snipped shape can be customized and inserted using the `InsertShape` method.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where you want to save the document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a New Document and DocumentBuilder
Create a new instance of the `Document` class and a `DocumentBuilder` object to work with the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Insert the Corners Snipped Shape
Use the `InsertShape` method of the `DocumentBuilder` object to insert a shape with corners snipped. Specify the shape type (in this case, `ShapeType.TopCornersSnipped`) and provide the desired size for the shape.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Step 4: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Example source code for Add Corners Snipped using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

That's it! You have successfully added a corners snipped shape to your Word document using Aspose.Words for .NET.
