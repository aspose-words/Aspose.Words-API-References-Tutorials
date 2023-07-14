---
title: Remove Document Protection In Word Document
linktitle: Remove Document Protection In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to remove protection in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/remove-document-protection/
---
In this tutorial, we will guide you through the steps to use the unprotect document feature of Aspose.Words for .NET. This feature allows you to remove protection in a Word document to make it accessible for further editing. Follow the steps below:

## Step 1: Creating the Document and Adding Content

Start by creating an instance of the Document class and a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Add content to the document

Use the DocumentBuilder object to add content to the document:

```csharp
builder.Writeln("Text added to a document.");
```

## Step 3: Unprotect Document

To unprotect the document, you can use the Unprotect() method of the Document object. You can choose to remove protection without password or with correct password. Removing passwordless protection:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Be sure to replace "newPassword" with the correct document password.

## Step 4: Save the document without protection

Finally, save the document unprotected using the Save() method of the Document object:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Be sure to specify the correct path and filename to save the document unprotected.

### Example source code for Remove Document Protection using Aspose.Words for .NET

Here is the complete source code for unprotecting the document using Aspose.Words for .NET:

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// Documents can have protection removed either with no password, or with the correct password.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

By following these steps, you can easily remove protection from Word document with Aspose.Words for .NET.

## Conclusion

In this tutorial, we explored how to remove document protection in a Word document using Aspose.Words for .NET. By following the provided steps, you can easily unprotect a document and make it accessible for further editing. Aspose.Words for .NET provides a powerful API that allows you to manipulate document protection settings and customize the level of security for your Word documents. Removing document protection gives you the flexibility to modify the document content and formatting as needed.

### FAQ's for remove document protection in word document

#### Q: What is document protection in Aspose.Words for .NET?

A: Document protection in Aspose.Words for .NET refers to the feature that allows you to apply security measures to a Word document to restrict editing, formatting, and content modifications. It helps ensure the integrity and confidentiality of the document.

#### Q: How can I remove document protection using Aspose.Words for .NET?

A: To remove document protection using Aspose.Words for .NET, you can follow these steps:
1. Create an instance of the `Document` class and a `DocumentBuilder` object.
2. Use the `DocumentBuilder` to add content to the document.
3. Call the `Unprotect` method of the `Document` object to remove any existing protection from the document. This can be done without a password or by providing the correct password.
4. Save the unprotected document using the `Save` method of the `Document` object.

#### Q: Can I remove protection from a Word document without a password?

A: Yes, you can remove protection from a Word document without a password using Aspose.Words for .NET. By calling the `Unprotect` method of the `Document` object without providing a password, you can remove protection from the document if it was previously protected without a password.

#### Q: How can I remove protection from a Word document with a password?

A: To remove protection from a Word document that was protected with a password, you need to provide the correct password when calling the `Unprotect` method of the `Document` object. This ensures that only users with the correct password can remove the protection and access the document for editing.

#### Q: Can I remove specific protection types from a Word document?

A: Yes, using Aspose.Words for .NET, you can selectively remove specific protection types from a Word document. By calling the `Unprotect` method of the `Document` object, you can remove the desired protection type, such as read-only protection or form protection, while leaving other protection types intact.
