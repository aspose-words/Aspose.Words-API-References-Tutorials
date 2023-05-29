---
title: Insert Html
linktitle: Insert Html
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert HTML content into Word documents using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-html/
---

In this comprehensive tutorial, you will learn how to insert HTML content into a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to add HTML elements, formatting, and styles to your Word documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert HTML Content
Next, use the InsertHtml method of the DocumentBuilder class to insert HTML content into the document. You can include HTML tags, attributes, and styling within the HTML string:

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## Step 3: Save the Document
After inserting the HTML content, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## Example Source Code for Insert HTML using Aspose.Words for .NET
Here is the complete source code for inserting HTML content into a Word document using Aspose.Words for .NET:
This feature is particularly useful when you have existing HTML content that you want to include in your Word documents while preserving the original formatting and layout.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

Remember to adjust the code according to your specific HTML content and requirements. Ensure that your HTML is well-formed and compatible with Aspose.Words for .NET.

## Conclusion
Congratulations! You have successfully learned how to insert HTML content into a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now incorporate HTML elements, formatting, and styles within your Word documents.



