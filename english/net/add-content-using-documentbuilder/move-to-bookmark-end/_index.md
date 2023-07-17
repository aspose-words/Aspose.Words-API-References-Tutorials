---
title: Move To Bookmark End In Word Document
linktitle: Move To Bookmark End In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to use Aspose.Words for .NET to move to the end of a bookmark in Word documents with this step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/move-to-bookmark-end/
---
In this example, we will explore the Move To Bookmark End feature of Aspose.Words for .NET. Aspose.Words is a powerful document manipulation library that enables developers to create, modify, and convert Word documents programmatically. The Move To Bookmark End feature allows us to navigate to the end of a specific bookmark within a document and add content after it.

## Setting up the environment

Before we delve into the implementation details, let's make sure we have the necessary environment set up to work with Aspose.Words for .NET. Ensure you have the following:

- A working installation of Aspose.Words for .NET library
- Basic knowledge of C# programming language
- Access to a .NET development environment

## Understanding the Move To Bookmark End feature of Aspose.Words for .NET

The Move To Bookmark End feature allows you to navigate to the end of a bookmark within a Word document using Aspose.Words for .NET. This feature is useful when you want to add content after a specific bookmark in your document programmatically.

## Explaining the source code step by step

Let's break down the provided source code step by step to understand how to use the Move To Bookmark End feature in Aspose.Words for .NET.

## Step 1: Initializing the document and document builder

First, we need to initialize the `Document` and `DocumentBuilder` objects:

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Moving to the bookmark end

To move to the end of a bookmark, use the `MoveToBookmark` method of the `DocumentBuilder` class:

```csharp
builder.MoveToBookmark("MyBookmark1", false, true);
```

The `MoveToBookmark` method takes three parameters:
- Bookmark name: Provide the name of the bookmark you want to move to.
- IsBookmarkStart: Set to `false` to move to the end of the bookmark.
- IsBookmarkEnd: Set to `true` to indicate that you want to move to the bookmark end.

## Step 3: Adding content at the bookmark end

Once you have moved to the bookmark end, you can add content using the various methods provided by the `DocumentBuilder` class. In this example, we use the `Writeln` method to write a line of text:

```csharp
builder.Writeln("This is a bookmark.");
```

The `Writeln` method appends the specified text as a new paragraph at the current position of the `DocumentBuilder`.

### Example source code for Move To Bookmark End using Aspose.Words for .NET

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToBookmark("MyBookmark1", false, true);
builder.Writeln("This is a bookmark.");
```

## Conclusion

we explored the Move To Bookmark End feature of Aspose.Words for .NET. We learned how to navigate to the end of a bookmark and add content programmatically using the provided source code. This feature provides flexibility in manipulating Word documents using Aspose.Words for .NET.

### FAQ's for move to bookmark end in word document

#### Q: What is the purpose of the Move To Bookmark End feature in Aspose.Words for .NET?

A: The Move To Bookmark End feature in Aspose.Words for .NET allows developers to navigate to the end of a specific bookmark within a Word document programmatically. This feature is useful when you want to add content after a particular bookmark in the document.

#### Q: What are the prerequisites for using the Move To Bookmark End feature?

A: To work with the Move To Bookmark End feature, you need the following prerequisites:
1. A working installation of Aspose.Words for .NET library.
2. Basic knowledge of the C# programming language.
3. Access to a .NET development environment.

#### Q: Can I move to the start of a bookmark using this feature?

A: Yes, you can use the `MoveToBookmark` method with the parameter `IsBookmarkStart` set to `true` to move to the start of a bookmark.

#### Q: What happens if the specified bookmark does not exist in the document?

A: If the specified bookmark does not exist in the document, the `MoveToBookmark` method will not have any effect, and no content will be added at the bookmark end.

#### Q: Is it possible to add content at the start of the bookmark?

A: Yes, by setting the `IsBookmarkStart` parameter to `true`, you can move to the start of the bookmark and add content before it.
