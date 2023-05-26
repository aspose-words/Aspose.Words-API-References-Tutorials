---
title: Append Document To Blank
linktitle: Append Document To Blank
second_title: Aspose.Words for .NET API Reference
description: Learn how to append a document to a blank destination document in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/append-document-to-blank/
---

This tutorial explains how to use Aspose.Words for .NET to append the contents of one document to a blank destination document. The provided source code demonstrates how to create a new document, remove its content, and then append the source document to it.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from the official Aspose website or use NuGet package manager to install it.
- A document directory path where the source and destination documents are located.

## Step 2: Create a new destination document

Create a new `Document` object for the destination document.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Step 3: Remove existing content from the destination document

To ensure a clean destination document, remove all existing content from the document using the `RemoveAllChildren` method.

```csharp
dstDoc.RemoveAllChildren();
```

## Step 4: Append the source document to the destination document

Append the contents of the source document to the destination document using the `AppendDocument` method with `ImportFormatMode.KeepSourceFormatting` option.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 5: Save the destination document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

This completes the implementation of appending a document to a blank destination document using Aspose.Words for .NET.

### Example source code for Append Document To Blank using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// The destination document is not empty, often causing a blank page to appear before the appended document.
	// This is due to the base document having an empty section and the new document being started on the next page.
	// Remove all content from the destination document before appending.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```