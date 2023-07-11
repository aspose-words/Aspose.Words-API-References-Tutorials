---
title: Simple Append Document
linktitle: Simple Append Document
second_title: Aspose.Words Document Processing API
description: Learn how to join and append Word documents with preserved formatting using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/simple-append-document/
---

This tutorial will guide you through the process of using the Simple Append Document feature of Aspose.Words for .NET. This feature allows you to join and append Word documents with no additional options.

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

## Step 3: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 4: Save the Final Document

Finally, save the merged document with the Simple Append Document feature using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Example source code for Simple Append Document using Aspose.Words for .NET

Here's the full source code for the "Simple Append Document" feature in C# using Aspose.Words for .NET:

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Append the source document to the destination document using no extra options.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

That's it! You have successfully implemented the Simple Append Document feature using Aspose.Words for .NET. The final document will contain the merged content with the source formatting preserved.
