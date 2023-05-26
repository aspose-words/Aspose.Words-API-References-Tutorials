---
title: Create And Add Paragraph Node
linktitle: Create And Add Paragraph Node
second_title: Aspose.Words for .NET API Reference
description: Create and add a paragraph node to your Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-node/create-and-add-paragraph-node/
---

Here is a step by step guide to explain the C# source code below that illustrates how to create and add a paragraph node using Aspose.Words for .NET.

## Step 1: Import the necessary references
Before you begin, make sure you have imported the necessary references to use Aspose.Words for .NET into your project. This includes importing the Aspose.Words library and adding the required namespaces to your source file.

```csharp
using Aspose.Words;
```

## Step 2: Create a new document
In this step, we will create a new document using the `Document` class.

```csharp
Document doc = new Document();
```

## Step 3: Create a paragraph node
Now we will create a paragraph node using the `Paragraph` class and passing the document as a parameter.

```csharp
Paragraph para = new Paragraph(doc);
```

## Step 4: Access the document section
To add the paragraph to the document, we need to access the last section of the document using the `LastSection` property.

```csharp
Section section = doc.LastSection;
```

## Step 5: Add the paragraph node to the document
Now that we have the document section, we can add the paragraph node to the section using the `AppendChild` method on the section's `Body` property.

```csharp
section.Body.AppendChild(para);
```

## Step 6: Save the document
Finally, to save the document, you can use the `Save` method by specifying the desired output format, such as DOCX format.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### Sample Source Code for Create and Add Paragraph Node with Aspose.Words for .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

This is a complete code example to create and add a paragraph node using Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.
