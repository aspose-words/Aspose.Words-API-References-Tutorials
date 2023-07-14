---
title: Different Page Setup
linktitle: Different Page Setup
second_title: Aspose.Words Document Processing API
description: Learn how to append a document with different page setup settings using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/different-page-setup/
---

This tutorial explains how to use Aspose.Words for .NET to append a document with different page setup settings to another document. The provided source code demonstrates how to set up different page settings for the source and destination documents and ensure proper continuation and numbering.

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

## Step 3: Set up page settings for the source document

Adjust the page setup settings of the source document to ensure proper continuation and numbering. In this example, we set the section start to `SectionStart.Continuous` and restart page numbering. We also make sure that the page width, height, and orientation match the last section of the destination document.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Step 4: Modify paragraph formatting

To maintain proper formatting, iterate through all paragraphs in the source document and set the `KeepWithNext` property to `true`. This ensures that paragraphs stay together during the appending process.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Step 5: Append the source document to the destination document

Use the `AppendDocument` method of the destination document to append the modified source document to the destination document, preserving the source formatting.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 6: Save the destination document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

This completes the implementation of appending a document with different page setup settings using Aspose.Words for .NET.

### Example source code for Different Page Setup using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Set the source document to continue straight after the end of the destination document.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Restart the page numbering on the start of the source document.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// To ensure this does not happen when the source document has different page setup settings, make sure the
	// settings are identical between the last section of the destination document.
	// If there are further continuous sections that follow on in the source document,
	// this will need to be repeated for those sections.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Iterate through all sections in the source document.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```