---
title: Vertical Anchor
linktitle: Vertical Anchor
second_title: Aspose.Words Document Processing API
description: Learn how to position a shape vertically within a document using the vertical anchor feature in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-shapes/vertical-anchor/
---

This tutorial explains how to use the vertical anchor feature in Aspose.Words for .NET to position a shape vertically within a document. By setting the vertical anchor property of a shape, you can control its vertical alignment relative to the text or the page.

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

## Step 3: Insert and Configure a Shape
Insert a shape into the document using the `InsertShape` method of the `DocumentBuilder` object. Set the desired dimensions for the shape.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Step 4: Set the Vertical Anchor
Set the vertical anchor property of the shape to control its vertical alignment. In this example, we set it to "Bottom" to anchor the shape at the bottom of the text or page.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Step 5: Add Content to the Shape
Use the `MoveTo` method of the `DocumentBuilder` object to move the cursor to the first paragraph of the shape. Then, use the `Write` method to add content to the shape.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Step 6: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Example source code for Vertical Anchor using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

That's it! You have successfully used the vertical anchor feature in Aspose.Words for .NET to position a shape vertically within a document.
