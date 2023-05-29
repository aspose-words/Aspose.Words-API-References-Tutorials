---
title: Fenced Code
linktitle: Fenced Code
second_title: Aspose.Words for .NET API Reference
description: Learn how to use the fenced code feature with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/fenced-code/
---

In this example, we will walk you through how to use the fenced code feature with Aspose.Words for .NET. fenced code is used to represent blocks of code with specific formatting.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Adding a style for fenced code

We will add a custom style for the fenced code using the `Styles.Add` method of the `Document` object. In this example, we are creating a style called "FencedCode" for the fenced code.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Step 3: Adding fenced code without info

Now we can add a fenced code block with no information string using the "FencedCode" custom style.

```csharp
builder.Writeln("This is an fenced code");
```

## Step 4: Add fenced code with info string

We can also add a fenced code block with a string of information using another custom style. In this example, we are creating a style called "FencedCode.C#" to represent a block of C# code.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Example source code for Fenced Code using Aspose.Words for .NET

```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```



