---
title: Link Headers Footers
linktitle: Link Headers Footers
second_title: Aspose.Words for .NET API Reference
description: Learn how to link headers and footers while joining and appending Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/link-headers-footers/
---

This tutorial will guide you through the process of using the Link Headers Footers feature of Aspose.Words for .NET. This feature allows you to join and append multiple Word documents while linking the headers and footers of the source document to the previous section in the destination document.

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

## Step 3: Set the Appended Document to Appear on a New Page

To ensure that the content from the source document appears on a new page in the destination document, you need to set the `SectionStart` property of the first section in the source document to `SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Step 4: Link Headers and Footers to Previous Section

To link the headers and footers of the source document to the previous section in the destination document, you can use the `LinkToPrevious` method of the `HeadersFooters` collection. By passing `true` as the parameter, you override any existing headers or footers in the source document.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Step 5: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 6: Save the Final Document

Finally, save the merged document with the linked headers and footers using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Example source code for Link Headers Footers using Aspose.Words for .NET 

Here's the full source code for the "Link Headers Footers" feature in C# using Aspose.Words for .NET:


```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Set the appended document to appear on a new page.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Link the headers and footers in the source document to the previous section.
	// This will override any headers or footers already found in the source document.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

That's it! You have successfully implemented the Link Headers Footers feature using Aspose.Words for .NET. The final document will contain the merged content with the headers and footers from the source document linked to the previous section in the destination document.
