---
title: Owner Document
linktitle: Owner Document
second_title: Aspose.Words for .NET API Reference
description: Learn how to use the owner document in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-node/owner-document/
---

Here is a step-by-step guide to explain the C# source code below that illustrates how to use proprietary document functionality with Aspose.Words for .NET.

## Step 1: Import the necessary references
Before you begin, make sure you have imported the necessary references to use Aspose.Words for .NET into your project. This includes importing the Aspose.Words library and adding the required namespaces to your source file.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## Step 2: Create a new document
In this step, we will create a new document using the `Document` class.

```csharp
Document doc = new Document();
```

## Step 3: Create a node with the owner document
When you create a new node of any type, you must pass the document into the constructor. In this example, we are creating a new paragraph node using the document `doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## Step 4: Check parent node and owner document
Now that we have created the paragraph node, we can check if it has a parent node and if the owning document is the same as `doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Step 5: Modify node properties with document data
The relationship between a node and a document allows access and modification of properties that refer to document-specific data, such as styles or lists. In this example, we are setting the paragraph style name as "Heading 1".

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Step 6: Add the paragraph to the document
Now we can add the paragraph node to the main section of the document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Step 7: Verify parent node after adding
After adding the paragraph to the document, we check again if it now has a parent node.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Sample source code for owner document with Aspose.Words for .NET

```csharp
	Document doc = new Document();

	// Creating a new node of any type requires a document passed into the constructor.
	Paragraph para = new Paragraph(doc);

	// The new paragraph node does not yet have a parent.
	Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

	// But the paragraph node knows its document.
	Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

	// The fact that a node always belongs to a document allows us to access and modify
	// properties that reference the document-wide data, such as styles or lists.
	para.ParagraphFormat.StyleName = "Heading 1";

	// Now add the paragraph to the main text of the first section.
	doc.FirstSection.Body.AppendChild(para);

	// The paragraph node is now a child of the Body node.
	Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
            
```




