---
title: Insert Document At Mail Merge
linktitle: Insert Document At Mail Merge
second_title: Aspose.Words Document Processing API
description: Learn how to insert document into another during mail merge using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/clone-and-combine-documents/insert-document-at-mail-merge/
---

In this tutorial, we are going to walk you through how to insert a document into another document during mail merge using the Insert Document During Mail Merge feature of Aspose.Words for .NET. Follow the steps below to understand the source code and perform the document insertion.

## Step 1: Loading the main document

To get started, specify the directory for your documents and load the main document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Step 2: Configure Mail Merge

Now let's configure the mail merge and specify the field merge callback to insert a document into another document. Here's how:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Step 3: Running the Mail Merge

We'll run the mail merge by providing the names of the merge fields and the corresponding data. Here's how:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Example source code for Insert Document At Mail Merge using Aspose.Words for .NET

Here is the complete source code for the Insert Document in Mail Merge feature of Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// The main document has a merge field in it called "Document_1".
// The corresponding data for this field contains a fully qualified path to the document.
// That should be inserted to this field.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

With this code you will be able to insert a document into another document during mail merge using Aspose.Words for .NET. The resulting document will be saved under a new name




