---
title: Remove Table Of Contents
linktitle: Remove Table Of Contents
second_title: Aspose.Words Document Processing API
description: Learn how to remove the table of contents from a Word document using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/remove-content/remove-table-of-contents/
---

In this tutorial, we will walk you through how to remove the table of contents from a Word document using the Aspose.Words library for .NET. The table of contents can sometimes be redundant or unnecessary, and this code will help you remove it effectively. We'll provide a step-by-step guide to help you understand and implement the code in your own .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project
- A Word document containing a table of contents that you want to delete

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Upload the document
Next, we will load the Word document into an instance of the `Document` class using the `Load` method.

```csharp
// Load the document
Document doc = new Document(dataDir + "your-document.docx");
```

## Step 3: Delete the table of contents
To remove the table of contents, we will loop through the TOC (table of contents) type `FieldStart` nodes in the document. We will store these nodes so that we can quickly access them and create a list of nodes to delete.

```csharp
// Store FieldStart nodes of TOC fields in the document for quick access.
List<FieldStart> fieldStarts = new List<FieldStart>();
// This is a list to store the nodes found inside the specified TOC. They will be deleted at the end of this method.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Check if the specified TOC index exists.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // It's safer to store these nodes and delete them all at the end.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // When we encounter a FieldEnd node of type FieldTOC,
     // we know we are at the end of the current TOC and we stop here.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Sample source code for Remove Table Of Contents using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Load the document
Document doc = new Document(dataDir + "your-document.docx");

// Store the FieldStart nodes of TOC fields in the document for quick access.
List<FieldStart> fieldStarts = new List<FieldStart>();
// This is a list to store the nodes found inside the specified TOC. They will be removed at the end of this method.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Ensure the TOC specified by the passed index exists.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// It is safer to store these nodes and delete them all at once later.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Once we encounter a FieldEnd node of type FieldTOC,
	// we know we are at the end of the current TOC and stop here.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Conclusion
In this tutorial, we presented a step-by-step guide to remove the table of contents from a Word document using the Aspose.Words library for .NET. By following the provided code and instructions, you can easily eliminate the table of contents and improve the layout of your document. Remember to adapt the directory path and filenames to suit your specific needs.
