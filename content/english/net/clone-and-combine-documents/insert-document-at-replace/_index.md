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

## Conclusion

In this tutorial, we explored how to insert a document into another document during replace using the Insert Document When Replacing feature of Aspose.Words for .NET. By configuring the find and replace options and providing the necessary data, you can dynamically assemble documents by replacing specific placeholders with the contents of other document templates or sections. Aspose.Words for .NET offers a powerful and flexible way to manage complex document manipulation tasks, making it a valuable tool for automating document creation and content insertion scenarios.

### FAQ's

#### Q: What is the purpose of inserting a document into another document during replace?

A: Inserting a document into another document during replace allows you to dynamically replace a specific placeholder with the contents of a separate document. This feature is particularly useful when you want to assemble a larger document by combining various pre-defined document templates or sections into specific placeholders.

#### Q: How do I insert a document into another document during replace using Aspose.Words for .NET?

A: To insert a document into another document during replace using Aspose.Words for .NET, follow these steps:
1. Load the main document that contains the placeholders into a Document object.
2. Configure the find and replace options, including the search direction and replace callback to handle the document insertion.
3. Call the replace method with the appropriate search pattern, replacing the placeholders with an empty string, using the configured options.

#### Q: Can I customize the insertion behavior during replace?

A: Yes, you can customize the insertion behavior during replace by implementing a custom ReplacingCallback. By inheriting from the IReplacingCallback interface, you can control how the documents are inserted and merged based on your specific requirements when replacing the placeholders.

#### Q: Can I replace multiple placeholders with different documents?

A: Yes, you can replace multiple placeholders with different documents by specifying the appropriate search patterns for each placeholder and providing the corresponding documents to be inserted.
