---
title: Convert Metafiles To Png
linktitle: Convert Metafiles To Png
second_title: Aspose.Words Document Processing API
description: Learn how to convert metafiles to PNG images when uploading documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/convert-metafiles-to-png/
---
When working with documents in a C# application, it may be necessary to convert metafiles to PNG images for better compatibility and accurate rendering. With the Aspose.Words library for .NET, you can easily convert metafiles to PNG while loading a document. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to load a document with converting metafiles to PNG using the LoadOptions load options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Step 1: Defining the document directory

The first step is to define the directory where your documents are located. You must specify the full directory path. For example :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 2: Configuring Loading Options

Now let's configure the loading options for our document. Use the LoadOptions class to specify loading parameters. For example :

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };
```

In this example, we create a new LoadOptions object and set the ConvertMetafilesToPng property to true to enable conversion of metafiles to PNG when loading the document.

## Step 3: Loading the document with converting metafiles to PNG

Now that we have configured the load options, we can load the document using the Document class and specify the load options. For example :

```csharp
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

In this example, we are loading the document "WMF with image.docx" located in the documents directory using the specified load options.

## Example source code for the LoadOptions with Convert Metafiles To Png feature using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure loading options with the "Convert Metafiles To Png" feature
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };

// Load the document with the specified options
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

## Conclusion

In this guide, we explained how to load a document with converting metafiles to PNG images using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Converting metafiles to PNG ensures better compatibility and accurate rendering of documents.

