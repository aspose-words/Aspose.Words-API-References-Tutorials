---
title: Bulleted List
linktitle: Bulleted List
second_title: Aspose.Words for .NET API Reference
description: Learn how to create a bulleted list with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/bulleted-list/
---

In this tutorial, we are going to tell you how to create a bulleted list with Aspose.Words for .NET. A bulleted list is used to list items without using numbering.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Applying a Default Bulleted List

We can apply a default bulleted list using the document builder's `ApplyBulletDefault` method.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Step 3: Customizing the Bullet Format

We can customize the bullet format by accessing the properties of `ListFormat.List.ListLevels[0]`. In this example, we use the dash "-" as a bullet.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Step 4: Adding items to the list

Now we can add items to the bulleted list using the document builder's `Writeln` method.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Step 5: Removing indentation from the list

If we want to create a sublist, we can increase the indentation using the `ListFormat.ListIndent()` method. In this example, we are adding a sublist to items 2a and 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Example source code for Bulleted List using Aspose.Words for .NET


```csharp
// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Congratulation ! You have now learned how to create a bulleted list with Aspose.Words for .NET.

### FAQ's

#### Q: How to create a bulleted list in Markdown?

A: To create a bulleted list in Markdown, start each list item with a bullet symbol (`-`, `*`, or `+`), followed by a space.

#### Q: Can you nest bulleted lists in Markdown?

A: Yes, it is possible to nest bulleted lists in Markdown by adding four offset spaces in front of each nested list item.

#### Q: How to customize bullet symbols?

A: In standard Markdown, bullet symbols are predefined. However, some Markdown editors allow you to customize them using specific extensions.

#### Q: Do bulleted lists in Markdown support indentation?

A: Yes, bulleted lists in Markdown support indentation. You can add a left shift using spaces or tabs.

#### Q: Can links or inline text be added to list items?

A: Yes, you can add links or inline text to list items using the appropriate Markdown syntax.

