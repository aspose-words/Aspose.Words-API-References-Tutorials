---
title: Set Content Control Color
linktitle: Set Content Control Color
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the color of a content control in a Word document using Aspose.Words for .NET, customizing its appearance.
type: docs
weight: 10
url: /net/programming-with-sdt/set-content-control-color/
---

This tutorial explains how to set the color of a content control in a Word document using Aspose.Words for .NET. You can customize the appearance of content controls by changing their color.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document and Retrieve the Content Control
Load the Word document using the `Document` constructor, passing the path to the document as a parameter. Retrieve the desired content control from the document. In this example, we assume that the content control is the first structured document tag in the document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Step 3: Set the Content Control Color
Set the color of the content control by assigning a `Color` value to the `Color` property of the structured document tag. In this example, we set the color to red.

```csharp
sdt.Color = Color.Red;
```

## Step 4: Save the Document
Save the modified document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Example source code for Set Content Control Color using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

That's it! You have successfully set the color of a content control in your Word document using Aspose.Words for .NET.
