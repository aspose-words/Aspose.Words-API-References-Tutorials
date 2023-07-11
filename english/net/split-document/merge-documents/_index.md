---
title: Merge Documents
linktitle: Merge Documents
second_title: Aspose.Words Document Processing API
description: Step by step guide to explain C# source code of Merge Documents feature of Aspose.Words for .NET
type: docs
weight: 10
url: /net/split-document/merge-documents/
---

In this tutorial, we will walk you through how to merge multiple Word documents using the Merge Documents feature of Aspose.Words for .NET. Follow the steps below to understand the source code and get a merged document containing all source documents.

## Step 1: Search for documents to merge

Before merging the documents, we need to locate the source documents to be merged. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Search for documents to merge.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Step 2: Merge documents

Now we will merge the documents one by one to create a final merged document. Here's how:

```csharp
// Open the first part of the resulting document.
Document sourceDoc = new Document(sourceDocumentPath);

// Create a new resulting document.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Merge the documents one by one.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Example source code for Merge Documents using Aspose.Words for .NET

Here is the complete source code for the Merge Documents feature of Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Find documents using for merge.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Open the first part of the resulting document.
Document sourceDoc = new Document(sourceDocumentPath);

// Create a new resulting document.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Merge document parts one by one.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

