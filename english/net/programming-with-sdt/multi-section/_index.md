---
title: Multi Section
linktitle: Multi Section
second_title: Aspose.Words Document Processing API
description: Learn how to retrieve and process multi-section structured document tags in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/multi-section/
---

This tutorial explains how to work with multi-section structured document tags in a Word document using Aspose.Words for .NET. You can retrieve and process the section tags present in the document.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Begin by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document and Retrieve Multi-Section Tags
Load the Word document using the `Document` constructor, passing the path to the document as a parameter. Retrieve all the structured document tag range start nodes in the document using the `GetChildNodes` method.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Step 3: Process the Multi-Section Tags
Iterate through the collection of structured document tag range start nodes. In this example, we simply print the title of each tag to the console. You can perform further processing based on your requirements.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Example source code for Multi Section using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

That's it! You have successfully retrieved and processed multi-section structured document tags in your Word document using Aspose.Words for .NET.
