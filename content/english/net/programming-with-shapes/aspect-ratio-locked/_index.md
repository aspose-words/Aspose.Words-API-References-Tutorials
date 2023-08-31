---
title: Aspect Ratio Locked
linktitle: Aspect Ratio Locked
second_title: Aspose.Words Document Processing API
description: Learn how to lock or unlock the aspect ratio of a shape in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-shapes/aspect-ratio-locked/
---

This tutorial explains how to lock or unlock the aspect ratio of a shape in a Word document using Aspose.Words for .NET. By locking the aspect ratio, you can maintain the original proportions of the shape when resizing it.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and Words Processing with Word documents.

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

## Step 3: Insert an Image Shape
Use the `InsertImage` method of the `DocumentBuilder` object to insert an image shape into the document. Provide the path to the image file as a parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Step 4: Lock or Unlock the Aspect Ratio
Set the `AspectRatioLocked` property of the shape to `true` or `false` to lock or unlock the aspect ratio, respectively.

```csharp
shape.AspectRatioLocked = false; // Unlock the aspect ratio
```

## Step 5: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Example source code for Aspect Ratio Locked using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

That's it! You have successfully locked or unlocked the aspect ratio of a shape in your Word document using Aspose.Words for .NET.
