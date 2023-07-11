---
title: Move To Section
linktitle: Move To Section
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to using Move To Section in Aspose.Words for .NET manipulate sections and paragraphs in Word documents.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-section/
---

In this example, we will walk you through how to use the Move To Section feature of Aspose.Words for .NET step by step using the provided C# source code. This feature allows you to navigate and manipulate different sections inside a Word document. Follow the steps below to integrate this functionality into your application.

## Step 1: Create a new document and add a section

First, we need to create a new document and add a section to it. Use the following code to accomplish this step:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

This code creates a new empty document and adds a section to this document.

## Step 2: Move the DocumentBuilder to the second section and add text

Next, we need to move the DocumentBuilder to the second section of the document and add some text there. Use the following code to perform this step:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

This code creates a DocumentBuilder from the existing document, then moves the cursor from the DocumentBuilder to the second section of the document. Finally, it adds the specified text to this section.

## Step 3: Load a document with existing paragraphs

If you want to work with an existing document containing paragraphs, you can load this document using the following code:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

This code loads the specified document (replace "MyDir + "Paragraphs.docx"" with the actual path to your document) and accesses the collection of paragraphs from the first section of the document. The line `Assert.AreEqual(22, paragraphs.Count);` checks that the document contains 22 paragraphs.

## Step 4: create a DocumentBuilder for a document

You can create the DocumentBuilder cursor to a specific paragraph using positional indices.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Step 5: Move cursor to specific paragraph


You can move the DocumentBuilder cursor to a specific paragraph using positional indices. Here's how to do it:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

This code moves the cursor of the DocumentBuilder to the third paragraph of the second section (paragraph at index 2) and to position 10. Then it adds a new paragraph with some text and checks that the cursor is well positioned on this new paragraph .

### Example source code for Move To Move To Section using Aspose.Words for .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Move a DocumentBuilder to the second section and add text.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Create document with paragraphs.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// When we create a DocumentBuilder for a document, its cursor is at the very beginning of the document by default,
// and any content added by the DocumentBuilder will just be prepended to the document.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// You can move the cursor to any position in a paragraph.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

That's all ! You have now understood how to use the move to section functionality of Aspose.Words for .NET using the provided source code. You can now integrate this functionality into your own application and manipulate sections and paragraphs of your Word documents dynamically.


