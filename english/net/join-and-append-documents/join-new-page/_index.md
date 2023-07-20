---
title: Join New Page
linktitle: Join New Page
second_title: Aspose.Words Document Processing API
description: Learn how to join two documents on a new page while preserving formatting using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/join-new-page/
---

This tutorial explains how to join two documents on a new page using Aspose.Words for .NET. The provided source code demonstrates how to append a document to the end of another document while starting the appended document on a new page.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from [Aspose.Releases]https://releases.aspose.com/words/net/ or use NuGet package manager to install it.
- A document directory path where the source and destination documents are located.

## Step 2: Open the source and destination documents

Open the source and destination documents using the `Document` class constructor. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Step 3: Set up new page section start

To start the appended document on a new page, set the `SectionStart` property of the first section in the source document to `SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Step 4: Append the source document

Append the source document to the destination document using the `AppendDocument` method of the `Document` class. Set the import format mode to `ImportFormatMode.KeepSourceFormatting` to preserve the original styles from the source document.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 5: Save the modified document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

This completes the implementation of joining two documents on a new page using Aspose.Words for .NET.

### Example source code for Join New Page using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Set the appended document to start on a new page.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Append the source document using the original styles found in the source document.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```