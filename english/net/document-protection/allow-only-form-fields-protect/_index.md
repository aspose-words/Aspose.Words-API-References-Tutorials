---
title: Allow Only Form Fields Protect
linktitle: Allow Only Form Fields Protect
second_title: Aspose.Words Document Processing API
description: Learn how to use Aspose.Words for .NET to protect documents and only allow form fields to be edited.
type: docs
weight: 10
url: /net/document-protection/allow-only-form-fields-protect/
---

Document protection is an essential feature when working with files within your C# application. With the Aspose.Words library for .NET, you can easily protect your documents and only allow form fields to be edited. In this step-by-step guide, we will walk you through how to use C# source code to only allow form fields to be edited using the Allow Only Form Fields Protect feature of Aspose.Words for .NET.

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

