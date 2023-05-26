---
title: Optimize For Ms Word
linktitle: Optimize For Ms Word
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to optimizing a document for MS Word with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/optimize-for-ms-word/
---

In this tutorial, we will walk you through the C# source code to optimize a document for MS Word with Aspose.Words for .NET. This feature allows you to optimize a document for a specific version of MS Word.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document that we want to optimize. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Optimization for MS Word

Now let's optimize the document for a specific version of MS Word. Use the following code to perform the optimization:

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
```

This code tells Aspose.Words to optimize the document for MS Word 2016. You can replace `MsWordVersion.Word2016` with the specific version of MS Word you want to optimize.

### Example source code for Optimize For Ms Word using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
   
```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to optimize a document for a specific version of MS Word using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily optimize your own documents for different versions of MS Word.
