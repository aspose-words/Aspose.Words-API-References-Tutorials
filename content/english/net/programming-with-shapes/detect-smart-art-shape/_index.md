---
title: Detect Smart Art Shape
linktitle: Detect Smart Art Shape
second_title: Aspose.Words Document Processing API
description: Learn how to detect Smart Art shapes in a Word document using Aspose.Words for .NET, identifying graphical representations.
type: docs
weight: 10
url: /net/programming-with-shapes/detect-smart-art-shape/
---

This tutorial explains how to detect Smart Art shapes in a Word document using Aspose.Words for .NET. Smart Art shapes are graphical representations used to visually present information and ideas.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and Words Processing with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document
Load the Word document using the `Document` constructor, passing the path to the document as a parameter.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Step 3: Detect Smart Art Shapes
Iterate through the child nodes of type `Shape` in the document using the `GetChildNodes` method. Check if each shape has Smart Art using the `HasSmart Art` property.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Step 4: Output the Result
Print the count of shapes with Smart Art detected in the document.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Example source code for Detect Smart Art Shape using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

That's it! You have successfully detected Smart Art shapes in your Word document using Aspose.Words for .NET.
