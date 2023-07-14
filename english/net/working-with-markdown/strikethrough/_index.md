---
title: Strikethrough
linktitle: Strikethrough
second_title: Aspose.Words Document Processing API
description: Learn how to apply the strikethrough text style with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/strikethrough/
---


In this example, we will walk you through how to apply the strikethrough text style using Aspose.Words for .NET. Strikethrough text is used to indicate that the text is deleted or no longer valid.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Apply strikethrough text style

We will enable the strikethrough text style by setting the `StrikeThrough` property of the `Font` object to `true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Step 3: Add strikethrough text

We can now add strikethrough text using the document generator's `Writeln` method.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Example source code for strikethrough text with Aspose.Words for .NET

```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Make the text Strikethrough.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Congratulation ! You have now learned how to apply the strikethrough text style with Aspose.Words for .NET.

### FAQ's

#### Q: How can I add the strikethrough text in Aspose.Words?

A: To add the strikethrough text in Aspose.Words, you can use the `Font.StrikeThrough` property of the `Run` object. You can set this property to `true` to add strikethrough text to specific text. For example, you can use `run.Font.StrikeThrough=true` to add the strikethrough text into the `Run` object.

#### Q: Is it possible to add the strikethrough text to several pieces of text in the same paragraph?

A: Yes, you can add strikethrough text to multiple parts of text in a single paragraph by using multiple `Run` objects. You can create multiple `Run` objects and set the `Font.StrikeThrough` property to `true` for each object to add the strikethrough text to the desired text parts. Then you can add them to the paragraph using the `Paragraph.AppendChild(run)` method.

#### Q: Can I add strikethrough text to text that is in a table or cell in Aspose.Words?

A: Yes, you can add strikethrough text to text that is in a table or cell in Aspose.Words. You can jump to the cell or paragraph you want using the appropriate methods and then apply the strikethrough text formatting using the `Font.StrikeThrough` property of the `Run` or `Paragraph` object.
