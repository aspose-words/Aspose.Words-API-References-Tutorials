---
title: Enumerate Child Nodes
linktitle: Enumerate Child Nodes
second_title: Aspose.Words Document Processing API
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


### FAQ's

#### Q: What is a child node in Node.js?

A: A child node in Node.js refers to a node that is directly contained inside a specific node. These are the nodes that are immediately lower in the hierarchy than the parent node.

#### Q: How to enumerate the child nodes of a specific node?

A: To enumerate the child nodes of a specific node in Node.js, you can use the `childNodes` property of the node. This property returns a list of all child nodes of the specified node.

#### Q: How to access the properties of a child node?

A: To access the properties of a child node in Node.js, you can use the methods and properties provided by the XML API used in your Node.js environment. For example, you can use methods like `getAttribute` to get the value of a specific attribute of a child node.

#### Q: Can we modify the child nodes of a node?

A: Yes, it is possible to modify the child nodes of a node in Node.js using the methods and properties provided by the XML API used in your Node.js environment. For example, you can use methods like `appendChild` or `removeChild` to add or remove child nodes from a specific node.

#### Q: How to browse all child nodes of a node?

A: To loop through all child nodes of a specific node in Node.js, you can use a `for` loop to iterate through the list of child nodes returned by the `childNodes` property. You can then access the properties and values of each child node inside the loop.
