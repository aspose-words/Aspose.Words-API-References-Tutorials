---
title: Keep Source Numbering
linktitle: Keep Source Numbering
second_title: Aspose.Words Document Processing API
description: Learn how to append a document while preserving source numbering formatting in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/keep-source-numbering/
---

This tutorial explains how to append a source document to a destination document while preserving the original numbering formatting of numbered paragraphs using Aspose.Words for .NET.

## Step 1: Set up the project

Make sure you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from [Aspose.Releases]https://releases.aspose.com/words/net/ or use NuGet package manager to install it.
- A document directory path where the source and destination documents will be saved.

## Step 2: Create the destination and source documents

Create instances of `Document` for the destination and source documents.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Step 3: Keep source numbering when importing

To preserve the numbering formatting of numbered paragraphs from the source document, create an instance of `ImportFormatOptions` and set `KeepSourceNumbering` to `true`. Use a `NodeImporter` to import nodes from the source document to the destination document, specifying `ImportFormatMode.KeepSourceFormatting` and the `importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Step 4: Import and append paragraphs

Iterate through the paragraphs in the source document and import each paragraph into the destination document using the `importer`. Append the imported nodes to the destination document's body.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Step 5: Save the modified document

Save the modified document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

This completes the implementation of appending a source document to a destination document while keeping the original numbering formatting using Aspose.Words for .NET.

### Example source code for Keep Source Numbering using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Keep source list formatting when importing numbered paragraphs.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```