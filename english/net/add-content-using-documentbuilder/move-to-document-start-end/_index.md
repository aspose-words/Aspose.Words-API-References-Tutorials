---
title: Move To Document Start End
linktitle: Move To Document Start End
second_title: Aspose.Words for .NET API Reference
description: Learn how to use Aspose.Words for .NET to move to the document start and end in Word documents with this step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-document-start-end/
---

In this example, we will explore the Move To Document Start/End feature of Aspose.Words for .NET. Aspose.Words is a powerful document manipulation library that allows developers to create, modify, and convert Word documents programmatically. The Move To Document Start/End feature enables us to navigate to the beginning or end of a document using the DocumentBuilder class.

## Explaining the source code step by step

Let's go through the source code step by step to understand how to use the Move To Document Start/End feature using Aspose.Words for .NET.


## Step 1: Initializing the document and document builder

Next, initialize the Document and DocumentBuilder objects:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Moving to the document start

To move the cursor position to the beginning of the document, use the MoveToDocumentStart method of the DocumentBuilder class:

```csharp
builder.MoveToDocumentStart();
```

## Step 3: Moving to the document end

To move the cursor position to the end of the document, use the MoveToDocumentEnd method of the DocumentBuilder class:

```csharp
builder.MoveToDocumentEnd();
```

## Step 4: Outputting the cursor position

You can output the cursor position using Console.WriteLine or any other desired method. For example:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Example source code for Move To Document Start/End using Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Move the cursor position to the beginning of your document.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Move the cursor position to the end of your document.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Conclusion

In this example, we have explored the Move To Document Start/End feature of Aspose.Words for .NET. We learned how to navigate to the beginning and end of a document using the DocumentBuilder class. This feature is useful when programmatically working with Word documents and needing to manipulate or insert content at specific positions within the document.
