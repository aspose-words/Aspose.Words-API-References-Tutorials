---
title: Smart Style Behavior
linktitle: Smart Style Behavior
second_title: Aspose.Words Document Processing API
description: Learn how to maintain smart style behavior when joining and appending Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/smart-style-behavior/
---

This tutorial will guide you through the process of using the Smart Style Behavior feature of Aspose.Words for .NET. This feature allows you to join and append Word documents while maintaining smart style behavior.

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

## Step 3: Insert a Page Break in the Destination Document

To ensure that the appended content appears on a new page in the destination document, you can insert a page break using a `DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Step 4: Set Smart Style Behavior Options

To enable smart style behavior during the append operation, you need to create an instance of `ImportFormatOptions` and set the `SmartStyleBehavior` property to `true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Step 5: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `InsertDocument` method of the `DocumentBuilder` class. Use the `ImportFormatMode.UseDestinationStyles` parameter and pass the `ImportFormatOptions` object to maintain smart style behavior.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Step 6: Save the Final Document

Finally, save the merged document with the Smart Style Behavior feature enabled using the `Save` method of the `Document` class.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Example source code for Smart Style Behavior using Aspose.Words for .NET

Here's the full source code for the "Smart Style Behavior" feature in C# using Aspose.Words for .NET:
 
```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

That's it! You have successfully implemented the Smart Style Behavior feature using Aspose.Words for .NET. The final document will contain the merged content with smart style behavior maintained.
