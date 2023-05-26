---
title: Convert Shape To Office Math
linktitle: Convert Shape To Office Math
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert shapes to Office math formulas when uploading documents with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/convert-shape-to-office-math/
---

When working with documents containing math shapes in a C# application, you may need to convert them to Office math formulas for better compatibility and presentation. With the Aspose.Words library for .NET, you can easily convert shapes into Office math formulas while loading a document. In this step-by-step guide, we'll walk you through how to use Aspose.Words for .NET C# source code to load a document with converting shapes to Office math formulas using LoadOptions.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Configuring Loading Options

The first step is to configure the loading options for our document. Use the LoadOptions class to specify loading parameters. In our case, we want to convert the shapes to Office math formulas, so we need to set the ConvertShapeToOfficeMath property to true. Here's how to do it:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

We create a new LoadOptions object and set the ConvertShapeToOfficeMath property to true to enable converting shapes to Office math formulas when loading the document.

## Document loading with converting shapes to Office math formulas

Now that we have configured the load options, we can load the document using the Document class and specify the load options. Here is an example :

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

In this example, we load the document "Office math.docx" located in the documents directory using the load options specified.

## Registration of the document

After loading the document with converting shapes to Office math formulas, you can save it in the desired format using the Save method of the Document class. For example, to save the document in .docx format:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

Be sure to replace "dataDir" with the directory path to your documents.

### Example source code for LoadOptions with "Convert Shape To Office Math" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configuration of the loading options with the "Convert Shape" functionality

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// Load the document with the specified options
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

// Save the document in the desired format
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## Conclusion

In this guide, we explained how to load a document with converting shapes to Office math formulas using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Converting shapes to Office math formulas provides better compatibility and presentation of documents that contain math elements.

