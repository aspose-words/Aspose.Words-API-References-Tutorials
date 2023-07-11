---
title: Combo Box Content Control
linktitle: Combo Box Content Control
second_title: Aspose.Words Document Processing API
description: Learn how to create a Combo Box Content Control in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/combo-box-content-control/
---

This tutorial explains how to create a Combo Box Content Control in a Word document using Aspose.Words for .NET. Combo box content controls allow users to select an item from a dropdown list.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Begin by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where you want to save the document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a Document and StructuredDocumentTag
Create a new instance of the `Document` class and a `StructuredDocumentTag` to represent the combo box content control. Specify `SdtType.ComboBox` as the type and `MarkupLevel.Block` as the markup level to create a block-level combo box.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Step 3: Add Items to the Combo Box
Add items to the combo box by using the `ListItems` property of the `StructuredDocumentTag`. Each item is represented by an `SdtListItem` object, which takes a display text and a value. In this example, we add three items to the combo box.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Step 4: Append the StructuredDocumentTag to the Document
Append the combo box content control to the document's body by using the `AppendChild` method of the document's first section's body.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Step 5: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Example source code for Combo Box Content Control using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

That's it! You have successfully created a Combo Box Content Control in your Word document using Aspose.Words for .NET.
