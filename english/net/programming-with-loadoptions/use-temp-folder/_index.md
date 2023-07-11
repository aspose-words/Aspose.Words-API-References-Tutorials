---
title: Use Temp Folder
linktitle: Use Temp Folder
second_title: Aspose.Words Document Processing API
description: Learn how to use a temporary folder when uploading documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/use-temp-folder/
---

When working with Word documents in a C# application, it may be necessary to use a temporary folder to store temporary files generated during document processing. With the Aspose.Words library for .NET, you can easily specify a temporary folder using the LoadOptions load options. In this step-by-step guide, we'll show you how to use Aspose.Words for .NET C# source code to load a document using a temporary folder specified using the LoadOptions load options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Configuring loading options

The first step is to configure the loading options for our document. Use the LoadOptions class to specify loading parameters. In our case, we need to set the TempFolder property to the path of the desired temporary folder. Here's how to do it:

```csharp
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };
```

We create a new LoadOptions object and set the TempFolder property to the path of the desired temporary folder.

## Upload document using specified temporary folder

Now that we have configured the load options, we can load the document using the Document class and specify the load options. Here is an example :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

In this example, we load the document "Document.docx" located in the documents directory using the specified load options.

### Example source code for LoadOptions with "Use Temp Folder" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure loading options with the "Use Temp Folder" feature
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };

// Load the document using a specified temporary folder
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## Conclusion

In this guide, we explained how to upload a document using a specified temporary folder using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Using a temporary folder allows temporary files generated during document processing to be stored in an organized and efficient manner.

