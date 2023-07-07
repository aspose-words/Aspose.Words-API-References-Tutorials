---
title: Indented Code
linktitle: Indented Code
second_title: Aspose.Words for .NET API Reference
description: Learn how to use indented code with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/indented-code/
---

In this example, we will explain how to use the indented code feature with Aspose.Words for .NET. Indented code is used to visually represent blocks of code with specific formatting.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Add styling for indented code

We will add a custom style for the indented code using the `Styles.Add` method of the `Document` object. In this example, we are creating a style called "IndentedCode" for indented code.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Step 3: Add indented code

Now we can add an indented code block using the "IndentedCode" custom style.

```csharp
builder.Writeln("This is an indented code block");
```

### Example source code for indented code with Aspose.Words for .NET

```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Congratulation ! You have now learned how to use the indented code feature with Aspose.Words for .NET.


### FAQ's

#### Q: What is indented code in Markdown?

A: Indented code in Markdown is a formatting method used to display code in a Markdown document. It consists of indenting each line of code with spaces or tabs.

#### Q: How to use indented code in Markdown?

A: To use indented code in Markdown, indent each line of code with spaces or tabs.

#### Q: What are the advantages of indented code in Markdown?

A: Indented code in Markdown improves code readability and makes it easier for readers to understand.

#### Q: What is the difference between indented code and code blocks in Markdown?

A: Indented code is used for small code snippets inserted into text, while code blocks are used to display larger pieces of code in separate formatting.

#### Q: Is indented code in Markdown supported by all Markdown editors?

A: Support for indented code in Markdown may vary between Markdown editors. Check your publisher's specific documentation to be sure.
