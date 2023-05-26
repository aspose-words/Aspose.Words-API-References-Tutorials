---
title: Delete All Sections
linktitle: Delete All Sections
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to remove all sections from a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-section/delete-all-sections/
---
In this tutorial, we are going to tell you how to remove all sections from a Word document using the Aspose.Words library for .NET. Deleting sections can be useful to reorganize or simplify your document. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Create a document and constructor
First, we'll create an instance of the `Document` class and an associated `DocumentBuilder` constructor to build the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Add content and sections
Next, we'll use the `DocumentBuilder` constructor to add content and sections to the document. In this example, we're adding two lines of text and two sections.

```csharp
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello2");
doc.AppendChild(new Section(doc));
```

## Step 3: Delete all sections
To remove all sections from the document, we will use the `Clear` method of the `Sections` collection of the document.

```csharp
doc.Sections.Clear();
```

### Sample source code for Delete All Sections using Aspose.Words for .NET 
```csharp

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello2");
doc.AppendChild(new Section(doc));
doc.Sections.Clear();

```

## Conclusion
In this tutorial, we saw how to remove all sections from a Word document using Aspose.Words for .NET. Removing sections allows you to rearrange or simplify the structure of your document. Feel free to customize and use this feature to meet your specific needs.
