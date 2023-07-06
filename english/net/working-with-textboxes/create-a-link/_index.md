---
title: Create Link In Word
linktitle: Create Link In Word
second_title: Aspose.Words for .NET API Reference
description: Learn how to create link in word between TextBoxes in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-textboxes/create-a-link/
---
This step-by-step guide explains how to create link in word between two text boxes in a Word document using the Aspose.Words library for .NET. You will learn how to configure the document, create the text box shapes, access the text boxes, check the validity of the link target and finally create the link itself.

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
## Conclusion

Congratulation ! You have now learned how to create a link between two text boxes in a Word document using the Aspose.Words library for .NET. Using this step-by-step guide, you were able to set up the document, create the text box shapes, access the text boxes, check the validity of the link target, and finally create the link itself.

### FAQ's for create link in Word

#### Q: What is the library used to link text boxes in Word using Aspose.Words for .NET?

A: To link text boxes in Word using Aspose.Words for .NET, the library used is Aspose.Words for .NET.

#### Q: How to check if the link target is valid before creating the link?

A: Before creating the link between text boxes, you can use the `IsValidLinkTarget()` method to check if the link target is valid. This method validates whether the second text box can be a valid target for the link from the first text box.

#### Q: How to create a link between two text boxes?

A: To create a link between two textboxes, you need to set the `Next` property of the first textbox to the second textbox. Make sure you have checked the validity of the link target beforehand using the `IsValidLinkTarget()` method.

#### Q: Is it possible to create links between elements other than text boxes?

A: Yes, using the Aspose.Words library for .NET, it is possible to create links between different elements such as paragraphs, tables, images, etc. The process will vary depending on the specific item you wish to link.

#### Q: What other functionality can be added to text boxes in Word using Aspose.Words for .NET?

A: With Aspose.Words for .NET, you can add many other features to text boxes, such as text formatting, adding images, changing styles, etc. You can explore the Aspose.Words for .NET documentation to find out all the features available.
