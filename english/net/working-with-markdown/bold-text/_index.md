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



