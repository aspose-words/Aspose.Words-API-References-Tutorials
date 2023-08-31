---
title: Do Not Compress Small Metafiles
linktitle: Do Not Compress Small Metafiles
second_title: Aspose.Words Document Processing API
description: Learn how to use Aspose.Words for .NET to enable the Do Not Compress Small Metafiles feature when saving documents.
type: docs
weight: 10
url: /net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

Compressing metadata in a document is a common feature when Words Processing with files in a C# application. However, it may be necessary not to compress the metadata of small files to preserve their quality. In this step-by-step guide, we'll show you how to use the C# source code of Aspose.Words for .NET to enable the "Do Not Compress Small Metafiles" feature in the document save options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Step 1: Set Document Directory

The first step is to define the directory where you want to save the document. You must specify the full directory path. For example :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 2: Insert sections and text

Then you can insert sections and text into your document. Use the DocumentBuilder class provided by Aspose.Words to build the content of your document. Here is a simple example:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In this example, we create a new blank document and then use DocumentBuilder to add a line of text.

## Step 3: Setup Options

'registration

Now let's configure the save options for our document. Use the DocSaveOptions class to specify save settings. For example :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

In this example, we are creating a new DocSaveOptions object to set save options.

## Step 4: Enable "Do Not Compress Small Metafiles" Feature

To enable the "Do Not Compress Small Metafiles" feature, you must set the `Compliance` property of the DocSaveOptions object to the value `PdfCompliance.PdfA1a`. Here's how:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

This configuration ensures that small file metadata is not compressed when the document is saved.

## Step 5: Save the document

Finally, you can save the document using the `Save` method of the Document class. Specify the full path to the file and the desired file name. For example :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Be sure to replace "dataDir" with the path to your document directory.

### Example source code for DocSaveOptions with Do Not Compress Small Metafiles feature using Aspose.Words for .NET

```csharp
// Path to your document directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Insert two sections with some text.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Configure save options with "Do Not Compress Small Metafiles" feature
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Save the document with the specified options
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Conclusion

In this guide, we explained how to use the Aspose.Words library for .NET to enable the "Do Not Compress Small Metafiles" feature when saving a document. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Preserving uncompressed small file metadata can be important to maintaining document quality and integrity.
