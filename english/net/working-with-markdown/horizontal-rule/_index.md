---
title: Horizontal Rule
linktitle: Horizontal Rule
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert a horizontal rule with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/horizontal-rule/
---

In this example, we are going to show you how to use the horizontal rule feature with Aspose.Words for .NET. Horizontal Rule are used to visually separate sections of a document.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Inserting a horizontal rule

We can insert a horizontal rule using the `InsertHorizontalRule` method of the document generator.

```csharp
builder. InsertHorizontalRule();
```

## Sample source code for horizontal rule with Aspose.Words for .NET

```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

// Insert horizontal rule.
builder.InsertHorizontalRule();
```

Congratulation ! You have now learned how to use the horizontal rule feature with Aspose.Words for .NET.


### FAQ's

#### Q: How do I create a horizontal ruler in Markdown?

A: To create a horizontal ruler in Markdown, you can use one of the following symbols on an empty line: three asterisks (\***), three dashes (\---), or three underscores (\___).

#### Q: Can I customize the appearance of a horizontal ruler in Markdown?

A: In standard Markdown, there is no way to customize the appearance of horizontal rulers. However, some advanced Markdown editors and extensions offer additional customization features.

#### Q: Are horizontal rulers supported by all Markdown editors?

A: Yes, most popular Markdown editors support horizontal rulers. However, it's always best to check your specific vendor's documentation to make sure it's supported.

#### Q: What other elements can I create in Markdown?

A: In addition to horizontal rulers, you can create titles, paragraphs, lists, links, images, tables, and more in Markdown.
