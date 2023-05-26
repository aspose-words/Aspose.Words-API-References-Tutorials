---
title: Restart Page Numbering
linktitle: Restart Page Numbering
second_title: Aspose.Words for .NET API Reference
description: Learn how to restart page numbering while joining and appending Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/restart-page-numbering/
---

This tutorial will guide you through the process of using the Restart Page Numbering feature of Aspose.Words for .NET. This feature allows you to join and append Word documents while restarting page numbering in the source document.

## Prerequisites

Before you begin, make sure you have the following:

1. Aspose.Words for .NET installed. You can download it from the Aspose website or install it via NuGet.
2. Visual Studio or any other C# development environment.

## Step 1: Initialize the Document Directories

First, you need to set the path to your document directory. Modify the value of the `dataDir` variable to the path where your documents are located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Source and Destination Documents

Next, you need to load the source and destination documents using the Aspose.Words `Document` class. Update the file names in the `Document` constructor according to your document names.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Step 3: Set the Source Document to Restart Page Numbering

To restart page numbering in the source document, you need to set the `SectionStart` property of the first section in the source document to `SectionStart.NewPage` and set the `RestartPageNumbering` property to `true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Step 4: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 5: Save the Final Document

Finally, save the merged document with the Restart Page Numbering feature enabled using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Example source code for Restart Page Numbering using Aspose.Words for .NET

Here's the full source code for the "Restart Page Numbering" feature in C# using Aspose.Words for .NET:
 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

That's it! You have successfully implemented the Restart Page Numbering feature using Aspose.Words for .NET. The final document will contain the merged content with page numbering restarted in the source document.
