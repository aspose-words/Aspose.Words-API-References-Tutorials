---
title: Get Protection Type In Word Document
linktitle: Get Protection Type In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to use the Get Protection Type in word document function of Aspose.Words for .NET to determine the protection type of a document.
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

### FAQ's

#### Q: What is the ProtectionType property in Aspose.Words for .NET?

A: The `ProtectionType` property in Aspose.Words for .NET is a feature that allows you to determine the type of protection applied to a Word document. It provides information about the level of document protection, such as whether the document is protected for comments, revisions, forms, or other types of restrictions.

#### Q: How can I retrieve the protection type of a document using Aspose.Words for .NET?

A: To retrieve the protection type of a document using Aspose.Words for .NET, you can follow these steps:
1. Load the document using the `Document` class.
2. Access the `ProtectionType` property of the `Document` object to retrieve the protection type.

#### Q: Can I determine if a document is protected for forms or form fields using the ProtectionType property?

A: Yes, you can determine if a document is protected for forms or form fields using the `ProtectionType` property in Aspose.Words for .NET. If the protection type is set to `AllowOnlyFormFields`, it indicates that the document is protected, and only form fields can be edited.

#### Q: What other protection types can the ProtectionType property return?

A: The `ProtectionType` property in Aspose.Words for .NET can return various protection types, including:
- `NoProtection`: The document is not protected.
- `AllowOnlyRevisions`: The document is protected, and only revisions can be made.
- `AllowOnlyComments`: The document is protected, and only comments can be added.
- `AllowOnlyFormFields`: The document is protected, and only form fields can be edited.
- `ReadOnly`: The document is protected and set as read-only.

#### Q: Can I modify the protection type of a document using the ProtectionType property?

A: No, the `ProtectionType` property in Aspose.Words for .NET is a read-only property. It allows you to retrieve the current protection type of a document but does not provide direct means to modify the protection type. To modify the protection type, you need to use other methods and properties available in the `Document` class, such as `Protect` or `Unprotect`.

#### Q: Is it possible to protect a document with multiple protection types simultaneously?

A: No, Aspose.Words for .NET allows only one protection type to be applied to a document at a time. However, you can combine different protection types by enabling protection, setting one type, disabling protection, and then enabling it again with another type.


