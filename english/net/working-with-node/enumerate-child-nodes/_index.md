---
title: Enumerate Child Nodes
linktitle: Enumerate Child Nodes
second_title: Aspose.Words for .NET API Reference
description: Learn how to enumerate child nodes in a paragraph with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-node/enumerate-child-nodes/
---

Here is a step by step guide to explain the C# source code below that illustrates how to enumerate child nodes using Aspose.Words for .NET.

## Step 1: Import the necessary references
Before you begin, make sure you have imported the necessary references to use Aspose.Words for .NET into your project. This includes importing the Aspose.Words library and adding the required namespaces to your source file.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## Step 2: Create a new document
In this step, we will create a new document using the `Document` class.

```csharp
Document doc = new Document();
```

## Step 3: Access the paragraph and its child nodes
To enumerate the child nodes of a paragraph, we first need to access the paragraph itself. Use the `GetChild` method with the `Paragraph` node type to get the first paragraph of the document.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

Next, we retrieve the collection of the paragraph's child nodes using the `ChildNodes` property.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## Step 4: Browse child nodes
Now that we have the collection of child nodes, we can loop through them using a `foreach` loop. We check the type of each child node and perform specific operations based on the type.

```csharp
foreach (Node child in children)
{
     // A paragraph can contain children of different types such as runs, shapes, and others.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

In this example, we are checking if the child node is of type `Run` (eg a text fragment). If so, we convert the node to `Run` and display the text using `run.Text`.

## Example source code for enumerating child nodes with Aspose.Words for .NET


```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

NodeCollection children = paragraph.ChildNodes;
foreach (Node child in children)
{
	// A paragraph may contain children of various types such as runs, shapes, and others.
	if (child.NodeType == NodeType.Run)
	{
		Run run = (Run) child;
		Console.WriteLine(run.Text);
	}
}
```

This is a complete code example to enumerate the child nodes of a paragraph with Aspose.Words for .NET. Make sure to import the references


