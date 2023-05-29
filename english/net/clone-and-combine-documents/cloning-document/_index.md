---
title: Cloning Document
linktitle: Cloning Document
second_title: Aspose.Words for .NET API Reference
description: Learn how to clone a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/clone-and-combine-documents/cloning-document/
---

In this tutorial, we are going to tell you how to clone a Word document using the clone feature of Aspose.Words for .NET. Follow the steps below to understand the source code and create an exact copy of an existing document.

## Step 1: Loading the document

To get started, specify your document directory and load the existing document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Step 2: Clone the document

Now we are going to clone the document creating an exact copy of it. Here's how:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Example source code for Cloning Document using Aspose.Words for .NET

Here is the complete source code for the Aspose.Words document clone feature for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

With this code you will be able to clone Word document using Aspose.Words for .NET. The exact copy of the document will be saved under a new file name.


