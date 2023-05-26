---
title: Create A Link
linktitle: Create A Link
second_title: Aspose.Words for .NET API Reference
description: Learn how to create a link between TextBoxes in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-textboxes/create-a-link/
---

## Step 1: Setting up the document and creating TextBox shapes

To start, we need to set up the document and create two TextBox shapes. The following code initializes a new instance of the `Document` class and creates two text box shapes:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Step 2: Creating a link between TextBoxes

We will now create a link between the two TextBoxes using the `IsValidLinkTarget()` method and the `Next` property of the first TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

The `IsValidLinkTarget()` method checks if the second TextBox can be a valid target for the link of the first TextBox. If the validation succeeds, the `Next` property of the first TextBox is set to the second TextBox, creating a link between the two.

### Example source code to link with Aspose.Words for .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```
