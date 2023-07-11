---
title: Append Document
linktitle: Append Document
second_title: Aspose.Words Document Processing API
description: Learn how to append the contents of one document to another using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/append-document/
---

This tutorial explains how to use Aspose.Words for .NET to append the contents of one document to another. The provided source code demonstrates how to open the source and destination documents, import and append sections from the source document to the destination document.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from the official Aspose website or use NuGet package manager to install it.
- A document directory path where the source and destination documents are located.

## Step 2: Open the source and destination documents

Open the source and destination documents using the `Document` class constructor. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Step 3: Append sections from the source document to the destination document

Loop through all sections in the source document and import each section into the destination document using the `ImportNode` method. Then, append the imported section to the destination document.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Step 4: Save the destination document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

This completes the implementation of appending a document using Aspose.Words for .NET.

### Example source code for Append Document using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Loop through all sections in the source document.
	// Section nodes are immediate children of the Document node so we can just enumerate the Document.
	foreach (Section srcSection in srcDoc)
	{
		// Because we are copying a section from one document to another, 
		// it is required to import the Section node into the destination document.
		// This adjusts any document-specific references to styles, lists, etc.
		//
		// Importing a node creates a copy of the original node, but the copy
		// ss ready to be inserted into the destination document.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Now the new section node can be appended to the destination document.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```