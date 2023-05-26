---
title: Add Custom Document Properties
linktitle: Add Custom Document Properties
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to add custom properties to a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/add-custom-document-properties/
---

In this tutorial, we will walk you through the C# source code to add custom properties to a document with Aspose.Words for .NET. This feature allows you to add custom information to the document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document to which we want to add custom properties. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Add custom properties

Now let's add custom properties to the document. Use the following code to add the properties:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

This code first checks if the "Authorized" property already exists in the custom properties. If it exists, the process is interrupted. Otherwise, the custom properties are added to the document.

### Example source code for Add Custom Document Properties using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to add custom properties to a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily add your own custom properties to your documents.
