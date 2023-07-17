---
title: Move To Document Start End In Word Document
linktitle: Move To Document Start End In Word Document
second_title: Aspose.Words Document Processing API
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

In this example, we have explored the Move To Document Start/End feature of Aspose.Words for .NET. We learned how to navigate to the beginning and end of a document using the DocumentBuilder class. This feature is useful when programmatically Words Processing with Word documents and needing to manipulate or insert content at specific positions within the document.

### FAQs

#### Q: What is the purpose of the Move To Document Start/End feature in Aspose.Words for .NET?

A: The Move To Document Start/End feature in Aspose.Words for .NET allows developers to navigate to the beginning or end of a Word document using the DocumentBuilder class. It is useful for programmatically manipulating or inserting content at specific positions within the document.

#### Q: Can I use this feature with an existing Word document?

A: Yes, you can use the Move To Document Start/End feature with both new and existing Word documents. Simply initialize the DocumentBuilder with the appropriate Document object, and then use the MoveToDocumentStart and MoveToDocumentEnd methods as shown in the example source code.

#### Q: How does the DocumentBuilder.MoveToDocumentStart/MoveToDocumentEnd method affect the document's content?

A: The DocumentBuilder.MoveToDocumentStart method moves the cursor to the beginning of the document without changing the existing content. Similarly, the DocumentBuilder.MoveToDocumentEnd method moves the cursor to the end of the document without altering the content.

#### Q: Can I perform other operations after moving the cursor to the document end?

A: Yes, after moving the cursor to the document end, you can continue using the DocumentBuilder to add or modify content at that position. The cursor's position remains at the end of the document until explicitly moved.

#### Q: How can I output the cursor position using Aspose.Words for .NET?

A: You can output the cursor position using methods like Console.WriteLine, logging, or any other desired output mechanism. In the example source code provided, Console.WriteLine is used to display messages for the beginning and end of the document.
