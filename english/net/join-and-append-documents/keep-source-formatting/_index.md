---
title: Keep Source Formatting
linktitle: Keep Source Formatting
second_title: Aspose.Words Document Processing API
description: Learn how to append a source document to a destination document while preserving the original formatting using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/keep-source-formatting/
---

This tutorial demonstrates how to append a source document to a destination document while preserving the original formatting of the source document using Aspose.Words for .NET.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from [Aspose.Releases]https://releases.aspose.com/words/net/ or use NuGet package manager to install it.
- A document directory path where the source and destination documents will be saved.

## Step 2: Create the destination and source documents

Create instances of `Document` for the destination and source documents.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Step 3: Append the source document to the destination document

Use the `AppendDocument` method of the destination document to append the source document. Pass `ImportFormatMode.KeepSourceFormatting` as the import format mode to retain the original formatting of the source document.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 4: Save the modified document

Save the modified document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

This completes the implementation of appending a source document to a destination document while keeping the original formatting using Aspose.Words for .NET.

### Example source code for Keep Source Formatting using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Append the source document to the destination document.
	// Pass format mode to retain the original formatting of the source document when importing it.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```