---
title: Check Sequence
linktitle: Check Sequence
second_title: Aspose.Words for .NET API Reference
description: Learn how to check the sequence of TextBoxes in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-textboxes/check-sequence/
---

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