---
title: Bold Text
linktitle: Bold Text
second_title: Aspose.Words for .NET API Reference
description: Learn how to bold text with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/bold-text/
---

In this example, we are going to tell you how to bold text with Aspose.Words for .NET. Bolding text makes it more visible and gives it more prominence.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Bold Text

We can bold the text by setting the document builder's `Font.Bold` property to `true`.

```csharp
builder.Font.Bold = true;
```

## Step 3: Add content to the document

Now we can add content to the document using the document builder methods, such as `Writeln`, which adds a line of text.

```csharp
builder.Writeln("This text will be bold");
```

## Example Source Code for Bold Text using Aspose.Words for .NET


```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Make the text Bold.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Congratulation ! You have now learned how to bold text with Aspose.Words for .NET.


### FAQ's

#### Q: How can I make text bold in Aspose.Words?

A: To make text bold in Aspose.Words, you can use the `Font.Bold` property of the `Run` object. You can set this property to `true` to bold specific text. For example, you can use `run.Font.Bold=true` to bold the text inside the `Run` object.

#### Q: Is it possible to bold several pieces of text in the same paragraph?

A: Yes, you can bold multiple pieces of text in a single paragraph using multiple `Run` objects. You can create multiple `Run` objects and set the `Font.Bold` property to `true` for each object to bold the desired parts of text. Then you can add them to the paragraph using the `Paragraph.AppendChild(run)` method.

#### Q: Can I bold text that is in a table or cell in Aspose.Words?

A: Yes, you can bold text that is in a table or cell in Aspose.Words. You can navigate to the cell or paragraph you want using the appropriate methods and then apply the bold formatting using the `Font.Bold` property of the `Run` or `Paragraph` object.
