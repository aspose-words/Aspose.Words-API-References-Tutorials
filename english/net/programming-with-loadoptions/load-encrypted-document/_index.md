---
title: Load Encrypted Document
linktitle: Load Encrypted Document
second_title: Aspose.Words for .NET API Reference
description: Learn how to load and save encrypted documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/load-encrypted-document/
---

When working with encrypted documents in a C# application, it is important to be able to load them correctly by providing the correct password. With the Aspose.Words library for .NET, you can easily load encrypted documents using the appropriate loading options. In this step-by-step guide, we'll show you how to use the C# source code of Aspose.Words for .NET to load an encrypted document using the LoadOptions load options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Loading an encrypted document

The first step is to upload an encrypted document using the appropriate upload options. In our case, we use the Document class to load the document by specifying the document path and password. Here is an example :

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

In this example, we load the document "Encrypted.docx" located in the documents directory using the password "password".

## Saving an encrypted document

After uploading an encrypted document, you can also save it by specifying a new password for the output file. In our example, we use the OdtSaveOptions class to save the document in ODT format with a new password. Here's how to do it:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

In this example, we save the document with the name "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt" by specifying the new password "newpassword".

### Sample source code for LoadOptions with "Load Encrypted Document" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load an encrypted document with the specified password
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

// Save an encrypted document with a new password
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Conclusion

In this guide, we explained how to load and save encrypted documents using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Uploading encrypted documents keeps your data safe and allows you to work with protected documents in Aspose.Words.
