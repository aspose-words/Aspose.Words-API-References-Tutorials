---
title: Encrypt Document With Password
linktitle: Encrypt Document With Password
second_title: Aspose.Words Document Processing API
description: Learn how to encrypt documents with a password using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Document security is essential when working with files in a C# application. With the Aspose.Words library for .NET, you can easily protect your documents by encrypting them with a password. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to encrypt a document using the DocSaveOptions save options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Step 1: Defining the document directory

The first step is to set the directory where you want to save the encrypted document. You must specify the full directory path. For example :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 2: Creating and editing a document

Then you can create a document and add content to it. Use the DocumentBuilder class provided by Aspose.Words to build the content of your document. For example :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

In this example, we create a new blank document and then use DocumentBuilder to write the text "Hello World!".

## Step 3: Configure recording options

Now let's configure the save options for our document. Use the DocSaveOptions class to specify save settings. For example :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

In this example, we create a new DocSaveOptions object and set the Password property to "password" to encrypt the document with this password.

## Step 4: Enabling "Encrypt Document With Password" Feature

We have already configured the options for

registration with the specified password, which automatically activates the "Encrypt Document With Password" feature. This ensures that the document is encrypted with the password specified when it was saved.

## Step 5: Saving the document

Finally, you can save the document using the Save method of the Document class. Specify the full path to the file and the desired file name. For example :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Be sure to replace "dataDir" with the directory path to your documents.

### Example source code for DocSaveOptions save options with "Encrypt Document With Password" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create and edit a document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Configure save options with the "Encrypt Document With Password" feature
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Save the document with the specified options
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Conclusion

In this guide, we explained how to use the Aspose.Words library for .NET to encrypt a document with a password using the DocSaveOptions save options. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Encrypting the document with a password guarantees its confidentiality and security when handling it.