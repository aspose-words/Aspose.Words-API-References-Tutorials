---
title: Remove Read Only Restriction
linktitle: Remove Read Only Restriction
second_title: Aspose.Words Document Processing API
description: Learn how to remove the read-only restriction from a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/remove-read-only-restriction/
---
In this tutorial, we will walk you through the steps to use Aspose.Words for .NET read-only restriction removal feature. This feature allows you to remove the read-only restriction from a Word document to make it editable. Follow the steps below:

## Step 1: Creating the Document and Setting the Protection

Start by creating an instance of the Document class:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Set a password for the document using the SetPassword() property of the WriteProtection object:

Be sure to replace "MyPassword" with the actual password you used to protect the document.

## Step 2: Remove read-only restriction

To remove the read-only restriction, set the ReadOnlyRecommended property to false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Step 3: Apply Unrestricted Protection

Finally, apply unrestricted protection using the Document object's Protect() method:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Be sure to specify the correct path and filename to save the document without the read-only restriction.

### Example source code for Remove Read Only Restriction using Aspose.Words for .NET

Here is the complete source code for removing the read-only restriction using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// Enter a password that's up to 15 characters long.
	doc.WriteProtection.SetPassword("MyPassword");

	// Remove the read-only option.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Apply write protection without any protection.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

By following these steps, you can easily remove the read-only restriction from a Word document with Aspose.Words for .NET.


