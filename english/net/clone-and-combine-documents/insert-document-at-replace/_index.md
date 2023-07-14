---
title: Insert Document At Replace
linktitle: Insert Document At Replace
second_title: Aspose.Words Document Processing API
description: Learn how to insert a document on replacement using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/clone-and-combine-documents/insert-document-at-replace/
---

In this tutorial, we will walk you through how to insert a document into another document when replacing using the Insert Document When Replacing feature of Aspose.Words for .NET. Follow the steps below to understand the source code and perform the document insertion.

## Step 1: Loading the main document

To get started, specify the directory for your documents and load the main document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Step 2: Configure search and replace options

Now we will configure the find and replace options by specifying the search direction and the replace callback to insert a document into another document. Here's how:

```csharp
// Configure search and replace options.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Step 3: Calling the replacement method

We will now call the replace method to find and replace the specified text with an empty string, using the configured options. Here's how:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Example source code for Insert Document At Replace using Aspose.Words for .NET

Here is the complete source code for the Insert Document feature when replacing Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Set find and replace options.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Call the replace method.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```
