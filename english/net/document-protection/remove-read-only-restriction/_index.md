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


## Conclusion

In this tutorial, we learned how to remove the read-only restriction from a Word document using Aspose.Words for .NET. By following the provided steps, you can easily remove the restriction and make the document editable again. Aspose.Words for .NET offers a comprehensive set of features for managing document protection and restrictions, providing you with flexibility and control over the security and editing capabilities of your Word documents.

### FAQ's

#### Q: What is the read-only restriction in Aspose.Words for .NET?

A: The read-only restriction in Aspose.Words for .NET refers to a feature that allows you to set a Word document as read-only, preventing users from making any modifications to the content or formatting. This restriction helps protect the integrity of the document and ensures that it is not accidentally or maliciously modified.

#### Q: How can I remove the read-only restriction using Aspose.Words for .NET?

A: To remove the read-only restriction from a Word document using Aspose.Words for .NET, you can follow these steps:
1. Create an instance of the `Document` class and set a password for the document using the `SetPassword` method of the `WriteProtection` object.
2. Set the `ReadOnlyRecommended` property of the `WriteProtection` object to `false` to remove the read-only recommendation.
3. Apply unrestricted protection to the document using the `Protect` method of the `Document` object with the `NoProtection` protection type.
4. Save the document without the read-only restriction using the `Save` method of the `Document` object.

#### Q: Can I remove the read-only restriction from a Word document without a password?

A: No, you cannot remove the read-only restriction from a Word document without providing the correct password. The read-only restriction is set for security purposes, and removing it without the password would undermine the purpose of protecting the document's integrity.

#### Q: Can I remove the read-only restriction from a Word document with the wrong password?

A: No, you cannot remove the read-only restriction from a Word document with the wrong password. The correct password must be provided to remove the read-only restriction and make the document editable again. This ensures that only authorized users with the correct password can modify the document.

#### Q: Is it possible to remove other types of document protection using Aspose.Words for .NET?

A: Yes, Aspose.Words for .NET provides various methods to remove other types of document protection, such as password protection, form protection, or document editing restrictions. Depending on the type of protection applied to the document, you can use the corresponding methods and properties provided by Aspose.Words to remove the specific protection and make the document editable.

