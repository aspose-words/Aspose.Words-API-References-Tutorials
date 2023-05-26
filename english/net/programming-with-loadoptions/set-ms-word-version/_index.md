---
title: Set Ms Word Version
linktitle: Set Ms Word Version
second_title: Aspose.Words for .NET API Reference
description: Learn how to load a document with a specified version of MS Word using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/set-ms-word-version/
---

When working with Word documents in a C# application, it may be necessary to specify the version of Microsoft Word to use when loading the document. With the Aspose.Words library for .NET, you can easily set which version of MS Word to use using LoadOptions. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to load a document with a specified version of MS Word using LoadOptions load options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Configuring Loading Options

The first step is to configure the loading options for our document. Use the LoadOptions class to specify loading parameters. In our case, we need to set the MswVersion property to the desired version of MS Word. For example, we are using Microsoft Word 2010 version. Here is how to do it:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

We create a new LoadOptions object and set the MswVersion property to MsWordVersion.Word2010 to specify the version of MS Word 2010.

## Document loading with specified version of MS Word

Now that we have configured the load options, we can load the document using the Document class and specify the load options. Here is an example :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

In this example, we load the document "Document.docx" located in the documents directory using the specified load options.

### Example source code for LoadOptions with "Set MS Word Version" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure load options with the "Set MS Word Version" feature
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Load the document with the specified version of MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Save the document
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Conclusion

In this guide, we have explained how to upload a document specifying a specific version of MS Word using the Aspose.Words library for .NET. By following the provided steps and using the code C# source provided, you can easily apply this functionality in your C# application. Loading a document with a specified version of MS Word allows you to ensure proper compatibility and processing of the document in your application.

