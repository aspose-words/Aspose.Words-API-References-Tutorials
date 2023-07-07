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


### FAQ's

#### Q: How can I use the inline code in Aspose.Words?

A: To use inline code in Aspose.Words, you can use appropriate tags to surround the text to be formatted as inline code. For example, you can use the `<code>` or `<kbd>` tag to surround text to be formatted as inline code.

#### Q: Is it possible to specify inline code font or color in Aspose.Words?

A: Yes, you can specify the font or color of the inline code in Aspose.Words. You can use the `Font.Name` and `Font.Color` properties of the `Run` object to set the font and color of inline code. For example, you can use `run.Font.Name = "Courier New"` to specify the font for inline code and `run.Font.Color = Color.Blue` to specify the color.

#### Q: Can I use the inline code in a paragraph containing other text elements?

A: Yes, you can use the inline code in a paragraph containing other text elements. You can create multiple `Run` objects to represent different parts of the paragraph, then use inline code tags to format only the specific parts as inline code. Then you can add them to the paragraph using the `Paragraph.AppendChild(run)` method.
