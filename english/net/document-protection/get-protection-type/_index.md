---
title: Get Protection Type
linktitle: Get Protection Type
second_title: Aspose.Words for .NET API Reference
description: Learn how to use the Get Protection Type function of Aspose.Words for .NET to determine the protection type of a document.
type: docs
weight: 10
url: /net/document-protection/get-protection-type/
---

Welcome to this step-by-step guide that explains the C# source code for the Get Protection Type feature of Aspose.Words for .NET. In this article, we'll show you how to use this powerful feature to determine a document's protection type. Document protection is essential to ensure the confidentiality and integrity of your files. We'll walk you through the steps needed to integrate Aspose.Words for .NET and use the Get Protection Type feature.

## Step 1: Loading the Document

The first step to using the Get Protection Type feature is to upload the document you want to work on. You can do this using the Document class provided by Aspose.Words for .NET. Here is a sample code to load a document from a file:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Be sure to specify the correct path to your document file.

## Step 2: Retrieving the Protection Type

After the document is uploaded, you can use the ProtectionType property of the Document object to retrieve the type of protection applied to the document. Here's how you can do it:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Example Source Code for Get Protection Type using Aspose.Words for .NET

Here is the complete source code for the Get Protection Type function using Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Document.docx");
	ProtectionType protectionType = doc.ProtectionType;

```

## Conclusion

In this article, we explained how to use the Get Protection Type function of Aspose.Words for .NET to determine the protection type of a document. By following the steps described, you will be able to easily integrate this functionality into your own C# projects and efficiently manipulate protected documents. Aspose.Words for .NET offers great flexibility


