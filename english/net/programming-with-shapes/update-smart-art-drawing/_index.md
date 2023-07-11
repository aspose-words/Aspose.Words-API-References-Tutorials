---
title: Update Smart Art Drawing
linktitle: Update Smart Art Drawing
second_title: Aspose.Words Document Processing API
description: Learn how to update the Smart Art drawing in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-shapes/update-smart-art-drawing/
---

This tutorial explains how to update the Smart Art drawing in a Word document using Aspose.Words for .NET. By iterating through the shapes in the document and checking if they have Smart Art, you can update the Smart Art drawing to reflect any changes made to its data.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document
Load the Word document that contains the Smart Art drawing using the `Document` class constructor.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Step 3: Update the Smart Art Drawing
Iterate through the shapes in the document using the `GetChildNodes` method with the `NodeType.Shape` parameter. Check if each shape has Smart Art using the `HasSmartArt` property, and if true, call the `UpdateSmartArtDrawing` method to update the Smart Art drawing.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Example source code for Update Smart Art Drawing using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

That's it! You have successfully updated the Smart Art drawing in your Word document using Aspose.Words for .NET.