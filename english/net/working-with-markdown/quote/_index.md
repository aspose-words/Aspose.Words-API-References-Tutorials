---
title: Quote
linktitle: Quote
second_title: Aspose.Words for .NET API Reference
description: Learn how to use quote with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/quote/
---

In this example, we will explain how to use the quote feature with Aspose.Words for .NET Quote are used to highlight sections of text by surrounding them with a special border.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Using the Default Citation Style

We'll use the default paragraph style called "Quote" to apply quote formatting to the text.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Step 3: Creating styles for nested levels

We can create styles for nested levels using the `Styles.Add` method of the `Document` object. In this example, we are creating a style called "Quote1" to represent a nested quote level.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Example source code for citations with Aspose.Words for .NET


```csharp
	// Use a document builder to add content to the document.
	DocumentBuilder builder = new DocumentBuilder();

	// By default a document stores blockquote style for the first level.
	builder.ParagraphFormat.StyleName = "Quote";
	builder.Writeln("Blockquote");

	// Create styles for nested levels through style inheritance.
	Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
	builder.ParagraphFormat.Style = quoteLevel2;
	builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
	builder.Writeln("1. Nested blockquote");
            
```

Congratulation ! You have now learned how to use the citations feature with Aspose.Words for .NET.


