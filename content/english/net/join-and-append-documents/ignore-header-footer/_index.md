---
title: Ignore Header Footer
linktitle: Ignore Header Footer
second_title: Aspose.Words Document Processing API
description: Learn how to append a document while ignoring header and footer content using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/ignore-header-footer/
---

This tutorial explains how to use Aspose.Words for .NET to append a document while ignoring the header and footer content. The provided source code demonstrates how to set up the import format options to exclude the header and footer during the appending process.

## Step 1: Set up the project

Ensure that you have the following prerequisites:

- Aspose.Words for .NET library installed. You can download it from [Aspose.Releases]https://releases.aspose.com/words/net/ or use NuGet package manager to install it.
- A document directory path where the source and destination documents are located.

## Step 2: Open the source and destination documents

Open the source and destination documents using the `Document` class constructor. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Step 3: Set up import format options

Create an instance of the `ImportFormatOptions` class and set the `IgnoreHeaderFooter` property to `false`. This ensures that the header and footer content is included during the appending process.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Step 4: Append the source document to the destination document

Use the `AppendDocument` method of the destination document to append the source document. Pass `ImportFormatMode.KeepSourceFormatting` as the second parameter and the import format options as the third parameter.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Step 5: Save the destination document

Finally, save the modified destination document using the `Save` method of the `Document` object.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

This completes the implementation of appending a document while ignoring the header and footer content using Aspose.Words for .NET.

### Example source code for Ignore Header Footer using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```