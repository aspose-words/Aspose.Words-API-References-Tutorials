---
title: Compare Options
linktitle: Compare Options
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to explain C# source code of Compare Options feature with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/compare-documents/compare-options/
---

In this tutorial, we will explain how to use the Compare Options feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Compare documents with custom options

To begin, load two documents to compare. In this example, we will use the `Clone()` method to create a copy of the original document. Here's how:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Step 2: Configuring comparison options

We will now configure the compare options by creating a `CompareOptions` object and setting the various properties as needed. Here's how:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Step 3: Compare documents with custom options

We will now use the `Compare()` method passing the custom options to compare the two documents. This method will mark the changes in the original document. Here's how:

```csharp
// Compare documents with custom options
docA.Compare(docB, "user", DateTime.Now, options);

// Check if the documents are equal
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Example source code for Compare Options using Aspose.Words for .NET

Here is the complete source code for the Compare Options feature with Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

With this code you can compare two documents using custom options to ignore specific elements when comparing with Aspose.Words for .NET.


