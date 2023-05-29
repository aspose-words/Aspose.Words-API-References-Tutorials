---
title: Get Parent Node
linktitle: Get Parent Node
second_title: Aspose.Words for .NET API Reference
description: Learn how to get the parent node of a specific element with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-node/get-parent-node/
---

Here is a step by step guide to explain the C# source code below that illustrates how to get the parent node using Aspose.Words for .NET.

## Step 1: Import the necessary references
Before you begin, make sure you have imported the necessary references to use Aspose.Words for .NET into your project. This includes importing the Aspose.Words library and adding the required namespaces to your source file.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
```

## Step 2: Create a new document
In this step, we will create a new document using the `Document` class.

```csharp
Document doc = new Document();
```

## Step 3: Access the parent node
To get the parent node of a specific node, we need to access that node first. In this example, we are accessing the first child node of the document, which is usually a section.

```csharp
Node section = doc.FirstChild;
```

## Step 4: Check the parent node
Now that we have the specific node, we can check if its parent node matches the document itself. In this example, we compare the parent node with the document using the equality operator (`==`) and display the result.

```csharp
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

### Sample source code to get parent node with Aspose.Words for .NET


```csharp
Document doc = new Document();

// The section is the first child node of the document.
Node section = doc.FirstChild;

// The section's parent node is the document.
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

This is a complete code example to get the parent node of a specific node with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.

