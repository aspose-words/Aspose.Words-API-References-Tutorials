---
title: Password Protection
linktitle: Password Protection
second_title: Aspose.Words for .NET API Reference
description: Learn how to password protection your Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/password-protection/
---

In this tutorial, we will guide you through the steps to use the password protection feature of Aspose.Words for .NET. This feature allows you to protect a Word document with a password to ensure its confidentiality. Follow the steps below:

## Step 1: Creating the Document and Applying Protection

Start by creating an instance of the Document class:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Step 2: Apply password protection

Then you can apply password protection using the Document object's Protect() method:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Be sure to replace "password" with the actual password you want to use to protect the document.

## Step 3: Saving the Protected Document

Finally, you can save the protected document using the Save() method of the Document object:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Be sure to specify the correct path and filename to save the protected document.

### Example source code for Password Protection using Aspose.Words for .NET

Here is the complete source code for password protection using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	// Apply document protection.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

Remember to replace "YOUR DOCUMENTS DIRECTORY" with the directory of your documents and "password" with the actual password you want to use.


