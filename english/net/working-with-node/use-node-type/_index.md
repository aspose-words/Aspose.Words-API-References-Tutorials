---
title: Use Node Type
linktitle: Use Node Type
second_title: Aspose.Words for .NET API Reference
description: Learn how to use node type to access document specific information with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-node/use-node-type/
---

Here is a step by step guide to explain the C# source code below that illustrates how to use the node type functionality with Aspose.Words for .NET.

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

## Step 3: Get Document Node Type
To get the node type of a document, we use the `NodeType` property.

```csharp
NodeType type = doc.NodeType;
```

### Sample Source Code for Using Node Type with Aspose.Words for .NET

```csharp
Document doc = new Document();

NodeType type = doc.NodeType;
```

This is a complete code example for using node type with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.


### FAQ's

#### Q: What is Node Type in Node.js?

A: Node Type in Node.js refers to the type of a node in an XML document. These can be types such as 1 (element), 2 (attribute), 3 (text), 4 (CDATA), 7 (processing instruction), etc.

#### Q: How to use Node Type to manipulate nodes in an XML document?

A: You can use Node Type to identify and manipulate different types of nodes in an XML document. For example, you can check if a node is an element, text, attribute, etc., and then perform specific operations accordingly.

#### Q: What are the common node types used with Node Type?

A: Common node types used with Node Type are elements (type 1), attributes (type 2), texts (type 3), CDATAs (type 4), processing instructions (type 7), etc.

#### Q: How do I check the type of a node in Node.js?

A: To check the type of a node in Node.js, you can access the `nodeType` property of the node. This property returns a number corresponding to the type of the node.

#### Q: Can new custom node types be created in Node.js?

A: In Node.js, it is not possible to create new custom node types. Node types are defined by XML specifications and cannot be extended.
