---
title: Remove Table Of Contents In Word Document
linktitle: Remove Table Of Contents In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to remove the table of contents in a Word document using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/remove-content/remove-table-of-contents/
---
In this tutorial, we will walk you through how to remove the table of contents in a Word document using the Aspose.Words library for .NET. The table of contents can sometimes be redundant or unnecessary, and this code will help you remove it effectively. We'll provide a step-by-step guide to help you understand and implement the code in your own .NET project.

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

### FAQ's

#### Q: Why should I use Aspose.Words to remove the table of contents in a Word document?

A: Aspose.Words is a powerful and versatile class library for manipulating Word documents in .NET applications. By using Aspose.Words, you can effectively remove the table of contents from your documents, which can be useful if the table of contents is redundant or unnecessary. This allows you to customize the content of your document and improve its overall presentation.

#### Q: How do I upload a document in Aspose.Words for .NET?

A: To remove the table of contents in a Word document, you must first load the document into memory using the Load() method of Aspose.Words. Here is sample code to load a document from a specific directory:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document
Document doc = new Document(dataDir + "your-document.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path to your document.

#### Q: How do I remove the table of contents in a document using Aspose.Words?

A: To remove the TOC, you need to iterate through the `FieldStart` type nodes of the TOC in the document. You can store these nodes for quick access and create a list of nodes to delete. Here is a sample code:

```csharp
// Store FieldStart nodes of TOC fields in the document for quick access.
List<FieldStart> fieldStarts = new List<FieldStart>();
// This is a list to store nodes found inside the specified TOC. They will be deleted at the end of this method.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Check if the specified table of contents index exists.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

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

#### Q: How to save edited document in Aspose.Words for .NET?

A: After deleting the table of contents, you must save the modified document using the Save() method. Specify the desired output file path and format (eg, DOCX) for the edited document. Here is a sample code:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```
