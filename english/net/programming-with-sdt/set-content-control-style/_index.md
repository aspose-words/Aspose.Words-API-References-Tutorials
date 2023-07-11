---
title: Set Content Control Style
linktitle: Set Content Control Style
second_title: Aspose.Words Document Processing API
description: Learn how to set the style of a content control in a Word document using Aspose.Words for .NET, applying consistent formatting.
type: docs
weight: 10
url: /net/programming-with-sdt/set-content-control-style/
---

This tutorial explains how to set the style of a content control in a Word document using Aspose.Words for .NET. You can apply pre-defined or custom styles to content controls for consistent formatting.

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

## Step 3: Retrieve the Style and Apply to Content Control
Retrieve the desired style from the document's styles collection. In this example, we retrieve the "Quote" style by using `StyleIdentifier.Quote`. Then, assign the retrieved style to the `Style` property of the structured document tag.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Step 4: Save the Document
Save the modified document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Example source code for Set Content Control Style using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

That's it! You have successfully set the style of a content control in your Word document using Aspose.Words for .NET.
