---
title: Unlink Headers Footers
linktitle: Unlink Headers Footers
second_title: Aspose.Words Document Processing API
description: Learn how to join and append Word documents while unlinking headers and footers using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/unlink-headers-footers/
---

This tutorial will guide you through the process of using the Unlink Headers Footers feature of Aspose.Words for .NET. This feature allows you to join and append Word documents while unlinking headers and footers from the source document.

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

## Step 3: Unlink Headers and Footers in the Source Document

To unlink the headers and footers in the source document from continuing the destination document's headers and footers, you need to set the `LinkToPrevious` property of the `HeadersFooters` collection in the first section of the source document to `false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Step 4: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 5: Save the Final Document

Finally, save the merged document with the Unlink Headers Footers feature enabled using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Example source code for Unlink Headers Footers using Aspose.Words for .NET

Here's the full source code for the "Unlink Headers Footers" feature in C# using Aspose.Words for .NET:

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Unlink the headers and footers in the source document to stop this
	// from continuing the destination document's headers and footers.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

That's it! You have successfully implemented the Unlink Headers Footers feature using Aspose.Words for .NET. The final document will contain the merged content with the headers and footers from the source document unlinked from the destination document.
