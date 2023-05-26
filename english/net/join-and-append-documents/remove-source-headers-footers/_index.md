---
title: Remove Source Headers Footers
linktitle: Remove Source Headers Footers
second_title: Aspose.Words for .NET API Reference
description: Learn how to remove headers and footers while joining and appending Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/remove-source-headers-footers/
---

This tutorial will guide you through the process of using the Remove Source Headers Footers feature of Aspose.Words for .NET. This feature allows you to join and append Word documents while removing headers and footers from the source document.

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

## Step 3: Remove Headers and Footers from Source Document Sections

To remove the headers and footers from each section in the source document, you can iterate through the sections using a `foreach` loop and call the `ClearHeadersFooters` method.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Step 4: Disable "LinkToPrevious" Setting for HeadersFooters

Even after clearing the headers and footers from the source document, there is a possibility that the "LinkToPrevious" setting for `HeadersFooters` can still be set. To avoid this behavior, you need to explicitly set it to `false` for the first section's `HeadersFooters` property.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Step 5: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 6: Save the Final Document

Finally, save the merged document with the Remove Source Headers Footers feature enabled using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Example source code for Remove Source Headers Footers using Aspose.Words for .NET 

Here's the full source code for the "Remove Source Headers Footers" feature in C# using Aspose.Words for .NET:


```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Remove the headers and footers from each of the sections in the source document.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Even after the headers and footers are cleared from the source document, the "LinkToPrevious" setting 
	// for HeadersFooters can still be set. This will cause the headers and footers to continue from the destination 
	// document. This should set to false to avoid this behavior.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
That's it! You have successfully implemented the Remove Source Headers Footers feature using Aspose.Words for .NET. The final document will contain the merged content with the headers and footers removed from the source document.
