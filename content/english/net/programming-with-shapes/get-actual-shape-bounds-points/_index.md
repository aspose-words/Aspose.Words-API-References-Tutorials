---
title: Get Actual Shape Bounds Points
linktitle: Get Actual Shape Bounds Points
second_title: Aspose.Words Document Processing API
description: Learn how to retrieve the actual bounds of a shape in points (measurement unit) in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-shapes/get-actual-shape-bounds-points/
---

This tutorial explains how to retrieve the actual bounds of a shape in points (measurement unit) in a Word document using Aspose.Words for .NET. The bounds represent the size and position of the shape within the document.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and Words Processing with Word documents.

## Step 1: Create a New Document and DocumentBuilder
Create a new instance of the `Document` class and a `DocumentBuilder` object to work with the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert an Image Shape
Use the `InsertImage` method of the `DocumentBuilder` object to insert an image shape into the document. Provide the path to the image file as a parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Step 3: Retrieve Actual Shape Bounds Points
Access the shape's `ShapeRenderer` using the `GetShapeRenderer` method. Then, retrieve the actual bounds of the shape in points using the `BoundsInPoints` property.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Example source code for Get Actual Shape Bounds Points using Aspose.Words for .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

That's it! You have successfully retrieved the actual bounds of a shape in points in your Word document using Aspose.Words for .NET.
