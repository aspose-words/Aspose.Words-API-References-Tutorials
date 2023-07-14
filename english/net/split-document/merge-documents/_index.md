---
title: Merge Word Documents
linktitle: Merge Documents
second_title: Aspose.Words Document Processing API
description: Learn how to merge multiple Word documents using Aspose.Words for .NET. This powerful API simplifies the process of merging documents, making it efficient and straightforward.
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

## Conclusion

Congratulations! You have learned how to merge multiple Word documents using the Merge Documents feature of Aspose.Words for .NET. By following the provided source code, you can combine separate documents into a single merged document while preserving the formatting of each source document.

Merging documents can be useful when you want to consolidate information from multiple sources or create a unified document from individual parts. Aspose.Words for .NET provides a powerful API that simplifies the process of merging documents, making it efficient and straightforward.

Feel free to explore other features offered by Aspose.Words for .NET to enhance your document processing capabilities and streamline your workflow.

### FAQs

#### How can I merge documents with different formatting?

When merging documents, Aspose.Words for .NET provides the option to preserve the formatting of each source document. By using the `ImportFormatMode.KeepSourceFormatting` option, the merged document will retain the formatting of the original documents. If you want to apply consistent formatting throughout the merged document, you can modify the formatting using the Aspose.Words API after merging the documents.

#### Can I merge documents in different formats?

Yes, Aspose.Words for .NET supports merging documents in various formats, including DOCX, DOC, RTF, and more. You can load documents of different formats into the Aspose.Words API and merge them into a single document regardless of their original formats.

#### Can I merge documents with complex structures, such as tables and images?

Absolutely! Aspose.Words for .NET is capable of merging documents with complex structures, including tables, images, headers, footers, and more. The API handles the merging process while preserving the integrity and layout of the content in each document.

#### Is it possible to merge documents with different page orientations or sizes?

Yes, Aspose.Words for .NET handles documents with different page orientations or sizes during the merging process. The resulting merged document will accommodate the varying page orientations and sizes of the source documents.
