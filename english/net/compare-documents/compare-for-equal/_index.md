---
title: Compare For Equal
linktitle: Compare For Equal
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to explain C# source code of Compare for Equals feature with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/compare-documents/compare-for-equal/
---

In this tutorial, we will walk you through how to use the Compare for Equal feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Document comparison

To begin, load two documents to compare. In this example, we will use the `Clone()` method to create a copy of the original document. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Step 2: Document comparison

We will now use the `Compare()` method to compare the two documents. This method will mark the changes in the original document. Here's how:

```csharp
// Compare the documents
docA.Compare(docB, "user", DateTime.Now);

// Check if the documents are equal
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Example source code for Compare For Equal using Aspose.Words for .NET

Here is the complete source code for the Compare for Equals feature with Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA now contains changes as revisions.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

With this code, you will be able to compare two documents and determine if they are the same using Aspose.Words for .NET.


