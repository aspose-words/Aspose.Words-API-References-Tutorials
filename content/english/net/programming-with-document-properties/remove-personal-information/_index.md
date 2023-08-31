---
title: Remove Personal Information
linktitle: Remove Personal Information
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to removing personal information from a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/remove-personal-information/
---

In this tutorial, we will walk you through the C# source code to remove personal information from a document with Aspose.Words for .NET. This feature allows you to remove sensitive personal information from a document, such as author identification data.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will upload the Word document from which we want to remove the personal information. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Delete personal information

Now we will enable the removal of personal information by setting the `RemovePersonalInformation` property to `true`. Use the following code:

```csharp
doc.RemovePersonalInformation = true;
```

This code activates the deletion of personal information in the document.

## Step 4: Saving the document

Finally, we will save the document with the personal information removed. Use the following code:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

This code saves the document with the personal information removed to a new file.

### Example source code for Remove Personal Information using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to remove personal information from a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily remove sensitive information from your own documents.
