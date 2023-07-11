---
title: Check Sequence
linktitle: Check Sequence
second_title: Aspose.Words Document Processing API
description: Learn how to check the sequence of TextBoxes in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-textboxes/check-sequence/
---
This step-by-step guide explains how to check the sequence of TextBoxes in a Word document using the Aspose.Words library for .NET. You will learn how to configure the document, create a TextBox shape, access TextBoxes and check their position in the sequence.

## Step 1: Setting up the document and creating a TextBox shape

To start, we need to set up the document and create a TextBox shape. The following code initializes a new instance of the `Document` class and creates a text box shape:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Step 2: Checking the TextBox sequence

We will now check the sequence of the TextBox using `if` conditions. The provided source code contains three separate conditions to check the position of the TextBox relative to the preceding and following shapes.

## Step 3: Checking the sequence head:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

If the TextBox has a next shape (`Next`) but no previous shape (`Previous`), that means it is the head of the sequence. The message "The head of the sequence" will be displayed.

## Step 4: Checking the middle of the sequence:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

If the TextBox has both a Next shape (`Next`) and a Previous shape (`Previous`), this indicates that it is in the middle of the sequence. The message "The middle of the sequence" will be displayed.

## Step 5: Verification of the end of the sequence:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

If the TextBox has no next shape (`Next`) but has a previous shape (`Previous`), that means it is the end of the sequence. The message "The end of the sequence" will be displayed.

### Sample source code to verify sequence with Aspose.Words for .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

## Conclusion

Congratulation ! You now know how to check the sequence of TextBoxes in a Word document using the Aspose.Words library for .NET. By following the steps in this guide, you were able to set up the document, create a TextBox shape, and check if it is at the head, middle, or end of the sequence.

### FAQ's for checking sequence

#### Q: What is the library used to check the sequence of TextBoxes using Aspose.Words for .NET?

A: To check the sequence of TextBoxes using Aspose.Words for .NET, the library used is Aspose.Words for .NET.

#### Q: How to determine if a TextBox is the head of the sequence?

A: To determine if a TextBox is the head of the sequence, you can check if it has a next form (`Next`) but not a previous form (`Previous`). If so, that means he is the head of the streak.

#### Q: How to know if a TextBox is in the middle of the sequence?

A: To determine if a TextBox is in the middle of the sequence, you need to check if it has both a next shape (`Next`) and a previous shape (`Previous`). If so, this indicates that it is in the middle of the sequence.

#### Q: How to check if a TextBox is the end of the sequence?

A: To check if a TextBox is the end of the sequence, you can check if it has no next form (`Next`) but has a previous form (`Previous`). If so, that means it's the end of the sequence.

#### Q: Can we check the sequence of elements other than TextBoxes?

A: Yes, using the Aspose.Words library for .NET, it is possible to check the sequence of other elements such as paragraphs, tables, images, etc. The process will vary depending on the specific item you want to check.

