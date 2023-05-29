---
title: Inline Code
linktitle: Inline Code
second_title: Aspose.Words for .NET API Reference
description: Learn how to inline code with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/inline-code/
---

In this example, we will walk you through how to use the inline code feature with Aspose.Words for .NET. Inline Code is used to visually represent pieces of code inside a paragraph.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Add styling for inline code

We will add a custom style for the inline code using the `Styles.Add` method of the `Document` object. In this example, we're creating a style called "InlineCode" for inline code with a default backtick.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Step 3: Add inline code

Now we can add inline code using the "InlineCode" custom style. In this example, we add two pieces of text with different numbers of backticks.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Example source code for Inline Code with Aspose.Words for .NET

```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Number of backticks is missed, one backtick will be used by default.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// There will be 3 backticks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Congratulation ! You have now learned how to use inline code functionality with Aspose.Words for .NET.


