---
title: Remove Document Protection
linktitle: Remove Document Protection
second_title: Aspose.Words Document Processing API
description: Learn how to remove protection from a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/remove-document-protection/
---

In this tutorial, we will guide you through the steps to use the unprotect document feature of Aspose.Words for .NET. This feature allows you to remove protection from a Word document to make it accessible for further editing. Follow the steps below:

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

