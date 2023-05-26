---
title: Rich Text Box Content Control
linktitle: Rich Text Box Content Control
second_title: Aspose.Words for .NET API Reference
description: Learn how to create a rich text box content control in a Word document using Aspose.Words for .NET enabling text formatting and styling.
type: docs
weight: 10
url: /net/programming-with-sdt/rich-text-box-content-control/
---

This tutorial demonstrates how to create a rich text box content control in a Word document using Aspose.Words for .NET. Rich text box content controls allow users to enter and format text with various styles and formatting options.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where you want to save the document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a Document and StructuredDocumentTag
Create a new instance of the `Document` class and a `StructuredDocumentTag` to represent the rich text box content control. Specify `SdtType.RichText` as the type and `MarkupLevel.Block` as the markup level to create a block-level rich text box.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Step 3: Create and Format the Rich Text Content
Create a paragraph and run to represent the rich text content. Set the text and formatting options such as color, font, etc.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Step 4: Add the Rich Text Content to the Content Control
Add the paragraph with the rich text content to the `ChildNodes` collection of the rich text box content control.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Step 5: Append the Content Control to the Document
Append the rich text box content control to the document's body by using the `AppendChild` method of the document's first section's body.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Step 6: Save the Document
Save the document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Example source code for Rich Text Box Content Control using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

That's it! You have successfully created a rich text box content control in your Word document using Aspose.Words for .NET.
