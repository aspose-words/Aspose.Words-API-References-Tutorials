---
title: Ignore Text Boxes
linktitle: Ignore Text Boxes
second_title: Aspose.Words for .NET API Reference
description: Learn how to append a document while ignore text box formatting using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/ignore-text-boxes/
---

This tutorial explains how to use Aspose.Words for .NET to append a document while preserving the formatting of text boxes. The provided source code demonstrates how to set up the import format options to include text boxes during the appending process.

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

## Step 3: Set up import format options

Create an instance of the `ImportFormatOptions` class and set the `IgnoreTextBoxes` property to `false`. This ensures that the text boxes are included during the appending process while preserving their formatting.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Step 4: Append text box content

Create a `NodeImporter` object and use it to import text box nodes from the source document to the destination document. Iterate through each paragraph in the source document and import it to the destination document.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Step 5: Save the destination document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

This completes the implementation of appending a document while preserving text box formatting using Aspose.Words for .NET.

### Example source code for Ignore Text Boxes using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Keep the source text boxes formatting when importing.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```