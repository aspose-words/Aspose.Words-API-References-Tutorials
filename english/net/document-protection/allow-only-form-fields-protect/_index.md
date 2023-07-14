---
title: Allow Only Form Fields Protect In Word Document
linktitle: Allow Only Form Fields Protect In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to use Aspose.Words for .NET to protect in word document and only allow form fields to be edited.
type: docs
weight: 10
url: /net/document-protection/allow-only-form-fields-protect/
---
Document protection is an essential feature when Words Processing with files within your C# application. With the Aspose.Words library for .NET, you can easily protect your documents and only allow form fields to be edited. In this step-by-step guide, we will walk you through how to use C# source code to only allow form fields to be edited using the Allow Only Form Fields Protect feature of Aspose.Words for .NET.

## Step 1: Setting the Document Directory

The first step is to define the directory of your document. You must specify the path where you want to save the protected document. For example :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 2: Inserting Sections and Text

Next, you need to insert sections and text into your document. Use the DocumentBuilder class provided by Aspose.Words to build the content of your document. Here is a simple example:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In this example, we create a new blank document and then use DocumentBuilder to add a line of text.

## Step 3: Enabling Document Protection

Document protection only works when document protection is enabled. You can enable document protection using the `Protect` method of the Document class. Here's how:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

In this example, we enable document protection by specifying the protection type `

AllowOnlyFormFields` and setting a password.

## Step 4: Allowing Only Form Fields

Now that document protection is enabled, we need to specify that only editing of form fields is allowed. This ensures that users can only edit parts of the document that are form fields. Here's how:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Be sure to replace "password" with the password you set earlier.

## Step 5: Saving the Protected Document

Finally, you can save the protected document using the `Save` method of the Document class. Specify the full file path and desired file name. For example :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Be sure to replace "dataDir" with the path to your document directory.

### Example source code for Allow Only Form Fields Protect feature using Aspose.Words for .NET

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Insert two sections with some text.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// A document protection only works when document protection is turned and only editing in form fields is allowed.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Save the protected document.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Conclusion

In this guide, we explored how to use the Aspose.Words library for .NET to protect a document and only allow form fields to be edited. By following the steps provided, you can easily implement this functionality in your C# application. Document protection is essential to ensure the security and confidentiality of your documents.

### FAQ's for allow only form fields protect in word document

#### Q: What is document protection in Aspose.Words for .NET?

A: Document protection in Aspose.Words for .NET is a feature that allows you to secure your documents by restricting certain actions, such as editing, formatting, or content modification. It helps maintain the integrity and confidentiality of your documents by preventing unauthorized changes.

#### Q: How can I protect a document and allow only form fields to be edited using Aspose.Words for .NET?

A: To protect a document and allow only form fields to be edited using Aspose.Words for .NET, you can follow these steps:
1. Define the directory path for your document.
2. Insert sections and text into your document using the `DocumentBuilder` class.
3. Enable document protection using the `Protect` method of the `Document` class, specifying the protection type as `AllowOnlyFormFields` and providing a password.
4. Save the protected document using the `Save` method of the `Document` class.

#### Q: Can I insert form fields into a protected document using Aspose.Words for .NET?

A: Yes, you can insert form fields into a protected document using Aspose.Words for .NET. The document protection with the `AllowOnlyFormFields` type allows users to edit only the form fields while protecting the rest of the document's content. You can use the `DocumentBuilder` class to insert form fields into the document before enabling protection.

#### Q: Can I remove document protection from a protected document?

A: Yes, you can remove document protection from a protected document using Aspose.Words for .NET. To remove the protection, you can use the `Unprotect` method of the `Document` class and provide the correct password. This will remove the protection and allow unrestricted editing of the document.

#### Q: Is it possible to protect a document with multiple protection types?

A: No, Aspose.Words for .NET allows only one protection type to be applied to a document at a time. However, the `AllowOnlyFormFields` protection type can effectively restrict editing to form fields while allowing other protection types, such as `AllowOnlyComments` or `AllowOnlyRevisions`, to be combined with form field protection.

#### Q: Can I set different passwords for different protection types in a document?

A: No, Aspose.Words for .NET allows you to set a single password for document protection, regardless of the protection type. The same password will be used to enable and disable document protection.
