---
title: Current State Of Check Box
linktitle: Current State Of Check Box
second_title: Aspose.Words for .NET API Reference
description: Learn how to retrieve and set the current state of a check box content control in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/current-state-of-check-box/
---

This tutorial explains how to retrieve and set the current state of a check box content control in a Word document using Aspose.Words for .NET. You can check or uncheck the check box based on its current state.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document and Retrieve the Check Box Content Control
Load the Word document using the `Document` constructor, passing the path to the document as a parameter. Then, retrieve the desired check box content control from the document. In this example, we assume that the check box is the first structured document tag in the document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Step 3: Check or Uncheck the Check Box Based on Its Current State
Check if the retrieved structured document tag is of type `SdtType.Checkbox`. If it is, set the `Checked` property of the content control to `true` to check the box. Otherwise, you can leave it unchecked.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Step 4: Save the Document
Save the modified document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Example source code for Current State Of Check Box using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Get the first content control from the document.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

That's it! You have successfully retrieved and set the current state of a check box content control in your Word document using Aspose.Words for .NET.
