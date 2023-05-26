---
title: Delete Section
linktitle: Delete Section
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to remove a specific section from a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-section/delete-section/
---

In this tutorial, we are going to show you how to delete a specific section of a Word document using the Aspose.Words library for .NET. Deleting a section can be useful for rearranging or deleting specific parts of your document. We'll take you step-by-step to help you understand and implement the code in your .NET project.

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

## Step 3: Delete a specific section
To remove a specific section of the document, we'll use the `RemoveAt` method of the document's `Sections` collection, specifying the index of the section to remove.

```csharp
doc.Sections.RemoveAt(0);
```

### Sample source code for Delete Section using Aspose.Words for .NET 

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.Writeln("Hello1");
	doc.AppendChild(new Section(doc));
	builder.Writeln("Hello2");
	doc.AppendChild(new Section(doc));
	doc.Sections.RemoveAt(0);

```

## Conclusion
In this tutorial, we saw how to remove a specific section from a Word document using Aspose.Words for .NET. Deleting sections allows you to rearrange or delete specific parts of your document. Feel free to customize and use this feature according to your specific needs.


