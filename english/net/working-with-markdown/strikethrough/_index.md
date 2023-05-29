---
title: Strikethrough
linktitle: Strikethrough
second_title: Aspose.Words for .NET API Reference
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

