---
title: Cursor Position
linktitle: Cursor Position
second_title: Aspose.Words Document Processing API
description: Learn how to retrieve the cursor position in a Word document using Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/cursor-position/
---

In this step-by-step example, you will learn about the cursor position in a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to retrieve the current node and paragraph where the cursor is positioned in the document.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Access the Current Node and Paragraph
Next, retrieve the current node and paragraph where the cursor is positioned. This can be achieved using the CurrentNode and CurrentParagraph properties of the DocumentBuilder class:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## Step 3: Retrieve Cursor Position Information
Now, you can retrieve information about the cursor position. In the following code snippet, we print the text of the current paragraph:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Example Source Code for Cursor Position using Aspose.Words for .NET
Here is the complete source code for understanding cursor position using Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Conclusion
Congratulations! You have successfully learned how to work with cursor position in a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now retrieve the current node and paragraph where the cursor is positioned in the document.

Understanding cursor position is useful for various scenarios, such as manipulating document content based on the cursor location or implementing custom editing features.


