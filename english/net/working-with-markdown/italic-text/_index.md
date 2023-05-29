---
title: Italic Text
linktitle: Italic Text
second_title: Aspose.Words for .NET API Reference
description: Learn how to italic text with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/italic-text/
---

In this example, we will walk you through how to use the italic text feature with Aspose.Words for .NET. Italic text is used to emphasize certain parts of a document.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Italicize Text

We can italicize text by setting the font's `Italic` property to `true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Example source code for italic text with Aspose.Words for .NET


```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Make the text Italic.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Congratulation ! You have now learned how to use the italic text feature with Aspose.Words for .NET.


