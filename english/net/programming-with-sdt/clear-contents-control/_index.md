---
title: Clear Contents Control
linktitle: Clear Contents Control
second_title: Aspose.Words for .NET API Reference
description: Learn how to clear the contents of a control in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/clear-contents-control/
---

This tutorial demonstrates how to clear the contents of a SDT in a Word document using Aspose.Words for .NET. Clearing the contents of an SDT removes any text or child nodes within the content control.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document and Get the StructuredDocumentTag
Load the Word document using the `Document` constructor, passing the path to the document as a parameter. Then, retrieve the desired `StructuredDocumentTag` from the document. In this example, we assume that the SDT is the first child node in the document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Step 3: Clear the Contents of the StructuredDocumentTag
Clear the contents of the SDT using the `Clear` method. This removes any text or child nodes within the content control.

```csharp
sdt.Clear();
```

## Step 4: Save the Document
Save the modified document using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Example source code for Clear Contents Control using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

That's it! You have successfully cleared the contents of a StructuredDocumentTag in your Word document using Aspose.Words for .NET.
