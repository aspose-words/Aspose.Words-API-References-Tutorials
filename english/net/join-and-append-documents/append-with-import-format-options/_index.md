---
title: Append With Import Format Options
linktitle: Append With Import Format Options
second_title: Aspose.Words Document Processing API
description: Learn how to append a document with import format options using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/append-with-import-format-options/
---

This tutorial explains how to use Aspose.Words for .NET to append the contents of one document to another with import format options. The provided source code demonstrates how to open the source and destination documents, specify import format options, and append the source document to the destination document.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from [Aspose.Releases]https://releases.aspose.com/words/net/ or use NuGet package manager to install it.
- A document directory path where the source and destination documents are located.

## Step 2: Open the source and destination documents

Open the source and destination documents using the `Document` class constructor. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Step 3: Specify import format options

Create an instance of the `ImportFormatOptions` class to specify the import format options. In this example, we use the `KeepSourceNumbering` property to ensure that numbering from the source document is used if there are clashes with the destination document.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Step 4: Append the source document to the destination document

Use the `AppendDocument` method of the destination document to append the source document. Pass `ImportFormatMode.UseDestinationStyles` as the second parameter to use the destination document's styles and formatting.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Step 5: Save the destination document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

This completes the implementation of appending a document with import format options using Aspose.Words for .NET.

### Example source code for Append With Import Format Options using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Specify that if numbering clashes in source and destination documents,
	// then numbering from the source document will be used.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```