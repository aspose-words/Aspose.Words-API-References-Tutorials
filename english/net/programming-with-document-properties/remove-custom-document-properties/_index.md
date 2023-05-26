---
title: Remove Custom Document Properties
linktitle: Remove Custom Document Properties
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to remove custom properties from a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/remove-custom-document-properties/
---

In this tutorial, we will walk you through the C# source code to remove custom properties from a document with Aspose.Words for .NET. This feature allows you to remove a specific custom property from a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document from which we want to remove the custom properties. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Deleting custom properties

Now let's remove a specific custom property from the document. Use the following code:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

This code removes the "Authorized Date" custom property from the document. You can replace "Authorized Date" with the name of the custom property you want to remove.

### Example source code for Remove Custom Document Properties using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to remove custom properties from a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily remove custom properties from your own documents.
