---
title: Show Grammatical And Spelling Errors
linktitle: Show Grammatical And Spelling Errors
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to enable display of grammatical and spelling errors in a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

In this tutorial, we will walk you through the C# source code to enable display of grammatical and spelling errors with Aspose.Words for .NET. This feature allows you to view grammatical and spelling errors in a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document for which we want to display grammatical and spelling errors. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Enable Error Display

Now we will enable the display of grammatical and spelling errors in the document. Use the following code to enable error display:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

This code enables the display of grammatical errors (`ShowGrammaticalErrors`) and spelling errors (`ShowSpellingErrors`) in the document.

### Example source code for Show Grammatical And Spelling Errors using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to enable the display of grammatical and spelling errors in a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily enable this feature in your own documents.
