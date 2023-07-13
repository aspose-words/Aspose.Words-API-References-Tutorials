---
title: Read Only Protection In Word Document
linktitle: Read Only Protection In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to protect your read-only in Word documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-protection/read-only-protection/
---
In this tutorial, we will guide you through the steps to use the read-only protection feature of Aspose.Words for .NET. This feature allows you to make a Word document read-only to prevent unauthorized modification. Follow the steps below:

## Step 1: Creating the Document and Applying Protection

Start by creating an instance of the Document class and a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Write content to the document
Use the DocumentBuilder object to write content to the document:

```csharp
builder.Write("Open document as read-only");
```

## Step 3: Set password and make document read-only

Set a password for the document using the SetPassword() property of the WriteProtection object:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Be sure to replace "MyPassword" with the actual password you want to use.

## Step 4: Apply read-only document

Make the document read-only by setting the ReadOnlyRecommended property to true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Step 5: Apply read-only protection and save the document

Finally, apply read-only protection using the Protect() method of the Document object:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Be sure to specify the correct path and filename to save the protected document.

### Example source code for Read Only Protection using Aspose.Words for .NET

Here is the complete source code for read-only protection using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// Enter a password that's up to 15 characters long.
	doc.WriteProtection.SetPassword("MyPassword");

	// Make the document as read-only.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Apply write protection as read-only.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

By following these steps, you can easily protect your documents

## Conclusion

In this tutorial, we explored the read-only protection feature of Aspose.Words for .NET, which allows you to make Word documents read-only to prevent unauthorized modifications. By following the provided steps, you can easily apply read-only protection to your documents and enhance their security. Read-only protection helps ensure the integrity and accuracy of your document's content by restricting editing capabilities. Aspose.Words for .NET provides a powerful and flexible API to handle document protection and supports various other features to customize and secure your Word documents.

### FAQ's for read only protection in word document

#### Q: What is read-only protection in Aspose.Words for .NET?

A: Read-only protection in Aspose.Words for .NET is a feature that allows you to make a Word document read-only, preventing unauthorized modifications. When a document is set to read-only, users can open and view the document, but they cannot make any changes to its content.

#### Q: How can I apply read-only protection to a Word document using Aspose.Words for .NET?

A: To apply read-only protection to a Word document using Aspose.Words for .NET, you can follow these steps:
1. Create an instance of the `Document` class and a `DocumentBuilder` object.
2. Use the `DocumentBuilder` to write content to the document.
3. Set a password for the document using the `SetPassword` method of the `WriteProtection` object.
4. Set the `ReadOnlyRecommended` property of the `WriteProtection` object to `true` to recommend opening the document as read-only.
5. Apply read-only protection using the `Protect` method of the `Document` object, specifying the `ProtectionType` as `ReadOnly`.
6. Save the protected document using the `Save` method of the `Document` object.

#### Q: Can I remove read-only protection from a Word document using Aspose.Words for .NET?

A: Yes, you can remove read-only protection from a Word document using Aspose.Words for .NET. To do this, you can use the `Unprotect` method of the `Document` class, which removes any existing protection from the document.

#### Q: Can I set a different password for read-only protection in a Word document?

A: No, the read-only protection in Aspose.Words for .NET does not allow you to set a separate password specifically for read-only protection. The password set using the `SetPassword` method of the `WriteProtection` object applies to the overall document protection, including both read-only and read-write protection.

#### Q: Can users bypass read-only protection in a Word document?

A: Read-only protection in a Word document is intended to discourage and prevent accidental or unauthorized modifications. While it provides a level of protection, it can be bypassed by users with sufficient technical knowledge or editing permissions. However, read-only protection serves as a deterrent and helps maintain the integrity of the document.
