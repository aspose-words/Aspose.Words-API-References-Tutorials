---
title: List Keep Source Formatting
linktitle: List Keep Source Formatting
second_title: Aspose.Words Document Processing API
description: Learn how to preserve list formatting while joining and appending Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/list-keep-source-formatting/
---

This tutorial will guide you through the process of using the List Keep Source Formatting feature of Aspose.Words for .NET. This feature allows you to join and append Word documents while preserving the source formatting of lists.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Step 3: Set the Source Document to Flow Continuously

To ensure that the content from the source document flows continuously when appended to the destination document, you need to set the `SectionStart` property of the first section in the source document to `SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Step 4: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting, including the formatting of lists, is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 5: Save the Final Document

Finally, save the merged document with the List Keep Source Formatting feature enabled using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Example source code for List Keep Source Formatting using Aspose.Words for .NET 

Here's the full source code for the List Keep Source Formatting feature in C# using Aspose.Words for .NET:

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Append the content of the document so it flows continuously.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

That's it! You have successfully implemented the List Keep Source Formatting feature using Aspose.Words for .NET. The final document will contain the merged content with the source document's list formatting preserved.
