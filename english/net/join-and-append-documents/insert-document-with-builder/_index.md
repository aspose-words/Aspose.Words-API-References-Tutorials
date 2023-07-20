---
title: Insert Document With Builder
linktitle: Insert Document With Builder
second_title: Aspose.Words Document Processing API
description: Learn how to insert a document at the end of another document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/insert-document-with-builder/
---

This tutorial explains how to use Aspose.Words for .NET to insert a document into another document using the `DocumentBuilder` class. The provided source code demonstrates how to insert a document at the end of another document while preserving the source formatting.

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

## Step 3: Initialize the DocumentBuilder

Create a new instance of the `DocumentBuilder` class and pass the destination document as a parameter.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Step 4: Position the DocumentBuilder

Move the `DocumentBuilder` to the end of the document using the `MoveToDocumentEnd` method. Insert a page break to separate the existing content from the inserted document.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Step 5: Insert the source document

Use the `InsertDocument` method of the `DocumentBuilder` class to insert the source document into the destination document. Set the import format mode to `ImportFormatMode.KeepSourceFormatting` to preserve the source formatting.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 6: Save the modified document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

This completes the implementation of inserting a document into another document using Aspose.Words for .NET.

### Example source code for Insert Document With Builder using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```