---
title: Move To Merge Field
linktitle: Move To Merge Field
second_title: Aspose.Words for .NET API Reference
description: Learn how to implement the Move To Merge Field feature in Aspose.Words for .NET using step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-merge-field/
---

In this example, we will explore the Move To Merge Field feature of Aspose.Words for .NET. Aspose.Words is a powerful document manipulation library that enables developers to create, modify, and convert Word documents programmatically. The Move To Merge Field feature allows us to navigate to merge fields within a document and perform various operations on them.


## Explaining the source code step by step

Let's go through the source code step by step to understand how to use the Move To Merge Field feature using Aspose.Words for .NET.

## Step 1: Initializing the document and document builder

First, initialize the Document and DocumentBuilder objects:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2 Inserting a merge field and adding text after it

Use the InsertField method of the DocumentBuilder class to insert a merge field, and then add text after it:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Step 3: The builder's cursor is currently at end of the document.

```csharp
Assert.Null(builder.CurrentNode);
```
## Step 4: Moving the document builder cursor to the merge field

To move the document builder cursor to the merge field, use the MoveToField method of the DocumentBuilder class:

```csharp
builder.MoveToField(field, true);
```

## Adding text immediately after the merge field

Once the document builder cursor is inside the merge field, you can add text immediately after it using the Write method:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Example source code for Move To Merge Field using Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a field using the DocumentBuilder and add a run of text after it.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// The builder's cursor is currently at end of the document.
Assert.Null(builder.CurrentNode);
// We can move the builder to a field like this, placing the cursor at immediately after the field.
builder.MoveToField(field, true);

// Note that the cursor is at a place past the FieldEnd node of the field, meaning that we are not actually inside the field.
// If we wish to move the DocumentBuilder to inside a field,
// we will need to move it to a field's FieldStart or FieldSeparator node using the DocumentBuilder.MoveTo() method.
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusion

we have explored the Move To Merge Field feature of Aspose.Words for .NET. We learned how to navigate to merge fields within a document using the DocumentBuilder class and perform operations on them. This feature is useful when programmatically working with merge


