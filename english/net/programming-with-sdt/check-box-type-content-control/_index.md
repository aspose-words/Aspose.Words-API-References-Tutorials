---
title: Check Box Type Content Control
linktitle: Check Box Type Content Control
second_title: Aspose.Words Document Processing API
description: Learn how to create a Check Box Type Content Control in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/check-box-type-content-control/
---

This tutorial explains how to create a Check Box Type Content Control in a Word document using Aspose.Words for .NET. Check box content controls allow users to select or clear a checkbox within the document.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where you want to save the document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a Document and DocumentBuilder
Create a new instance of the `Document` class and a `DocumentBuilder` to build the document's content.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Add a Check Box Type Content Control
Create a `StructuredDocumentTag` with `SdtType.Checkbox` to represent the check box content control. Specify `MarkupLevel.Inline` to place it within the text.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Step 4: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Example source code for Check Box Type Content Control using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

That's it! You have successfully created a Check Box Type Content Control in your Word document using Aspose.Words for .NET.
