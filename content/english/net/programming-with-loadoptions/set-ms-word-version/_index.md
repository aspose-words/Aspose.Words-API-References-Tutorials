---
title: Set Ms Word Version
linktitle: Set Ms Word Version
second_title: Aspose.Words Document Processing API
description: Learn how to load a document with a specified version of MS Word using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/set-ms-word-version/
---
When Words Processing with Word documents in a C# application, it may be necessary to specify the version of Microsoft Word to use when loading the document. With the Aspose.Words library for .NET, you can easily set which version of MS Word to use using LoadOptions. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to load a document with a specified version of MS Word using LoadOptions load options.

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


### FAQ's

#### Q: Why would I need to specify the version of MS Word when loading a document in a C# application?

Specifying the version of MS Word ensures that the document is loaded and processed correctly, especially when dealing with specific formatting or features that may vary between different versions.

#### Q: What versions of MS Word does Aspose.Words support?

A: Aspose.Words for .NET supports various versions of MS Word, including Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019, and more.

#### Q: Can I load a document with a different version of MS Word than the one installed on my system?

A: Yes, Aspose.Words allows you to specify a different version of MS Word when loading the document, ensuring compatibility even if the target system has a different MS Word version.

#### Q: How does setting the MS Word version benefit my C# application?

A: Setting the MS Word version ensures that the document is processed according to the intended formatting and features of that specific version, providing consistent output.

#### Q: Is Aspose.Words limited to handling only DOCX documents?

A: No, Aspose.Words supports various document formats, including DOC, RTF, HTML, PDF, and more, making it a versatile tool for handling different types of documents.
