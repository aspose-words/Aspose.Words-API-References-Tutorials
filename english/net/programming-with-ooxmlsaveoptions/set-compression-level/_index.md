---
title: Set Compression Level
linktitle: Set Compression Level
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the compression level when saving a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-ooxmlsaveoptions/set-compression-level/
---
In this tutorial, we will explore the provided C# source code to set the compression level when saving a document using Aspose.Words for .NET. This feature allows you to control the compression level of the generated document.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Loading the document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

In this step, we load the document using the `Document` method and passing the path to the DOCX file to load.

## Step 3: Configuring OOXML backup options

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

In this step, we configure OOXML save options using the `OoxmlSaveOptions` class. We set the compression level to `SuperFast` to get faster compression.

## Step 4: Save the document with the specified compression level

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

In this last step, we save the document using the `Save` method and passing the path to the output file with the `.docx` extension, along with the specified save options.

Now you can run the source code to set the compression level when saving a document. The resulting file will be saved in the specified directory with the name "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Sample source code for Set Compression Level using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Conclusion

In this tutorial, we explored the functionality of setting the compression level when saving a document using Aspose.Words for .NET. By specifying the appropriate level of compression, you can optimize document size and generation speed.

The `OoxmlSaveOptions` class provides flexibility to control the level of compression by setting the `CompressionLevel` property to an appropriate value, such as `SuperFast`. This allows you to strike the right balance between file size and backup speed based on your specific needs.

Using compression can be beneficial when you need to reduce the size of generated files, especially for large documents. This can make it easier to store, share, and transmit documents.

Aspose.Words for .NET offers a range of powerful options and features for document manipulation. By using the appropriate backup options, you can customize the document generation process and optimize your application's performance.

Feel free to explore more features of Aspose.Words for .NET to enhance your document generation workflow.

