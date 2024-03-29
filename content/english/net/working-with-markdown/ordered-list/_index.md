---
title: Ordered List
linktitle: Ordered List
second_title: Aspose.Words Document Processing API
description: Learn how to create ordered list with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/ordered-list/
---

In this example, we will explain how to use the ordered list functionality with Aspose.Words for .NET. Ordered List allow you to organize items sequentially with numbers.

## Step 1: Using a document generator

First, we'll use a document generator to create a new document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Applying the ordered list format

We will apply the ordered list format using the document builder's `ApplyBulletDefault` method. We can also customize the numbering format by going to the list levels and setting the format we want.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Step 3: Adding items to the list

We can add items to the list using the document generator's `Writeln` method.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Step 4: Indent the list

We can indent the list using the document generator's `ListIndent` method.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Step 5: Saving the document

Finally, we can save the document in the desired format.

### Example source code for ordered list with Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Congratulation ! You have now learned how to use the ordered list feature with Aspose.Words for .NET.


### FAQ's

#### Q: How to create an ordered list in Markdown?

A: To create an ordered list in Markdown, start each list item with a number followed by a period (`1.`, `2.`, `3.`), followed by a space.

#### Q: Can we nest ordered lists in Markdown?

A: Yes, it is possible to nest ordered lists in Markdown by adding four offset spaces in front of each nested list item.

#### Q: How to customize numbering of ordered lists?

A: In standard Markdown, ordered list numbering is generated automatically. However, some Markdown editors allow you to customize it using specific extensions.

#### Q: Do ordered lists in Markdown support indentation?

A: Yes, ordered lists in Markdown support indentation. You can add a left shift using spaces or tabs.

#### Q: Can links or inline text be added to list items?

A: Yes, you can add links or inline text to list items using the appropriate Markdown syntax.
