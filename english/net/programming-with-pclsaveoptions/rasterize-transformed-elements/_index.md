---
title: Rasterize Transformed Elements
linktitle: Rasterize Transformed Elements
second_title: Aspose.Words Document Processing API
description: Learn how to disable rasterization of transformed elements when converting to PCL format with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET is a powerful library for creating, manipulating and converting Word documents in a C# application. Among the features offered by Aspose.Words is the ability to rasterize transformed elements when converting documents to different formats. In this guide, we'll show you how to use the C# source code of Aspose.Words for .NET to disable rasterization of transformed elements when converting a document to PCL format.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a popular library that makes Words Processing with Word documents easy and efficient. It offers a wide range of features for creating, editing, and converting Word documents, including support for rasterizing transformed elements during conversion.

## Loading the Word document

The first step is to load the Word document you want to convert to PCL format. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

In this example, we are loading the "Rendering.docx" document located in the documents directory.

## Configuring backup options

The next step is to configure the save options for converting to PCL format. Use the PclSaveOptions class and set the RasterizeTransformedElements property to false. Here's how to do it:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

We create a new PclSaveOptions object and set the SaveFormat property to SaveFormat.Pcl to specify that we want to save the document in PCL format. Next, we set the RasterizeTransformedElements property to false to disable rasterization of transformed elements.

## Converting the document to PCL format

Now that we have configured the save options, we can proceed to convert the document to PCL format. Use the Save method of the Document class to save the converted document in PCL format by specifying save options. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

In this example, we save the converted document as "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" using the specified save options.

### Example source code for "Rasterize Transformed Elements" feature with Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the Word document


Document doc = new Document(dataDir + "Rendering.docx");

// Configure backup options for conversion to PCL format
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Convert the document to PCL format
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Conclusion

In this guide, we covered how to use Aspose.Words for .NET to disable rasterization of transformed elements when converting a document to PCL format using the provided C# source code. By following the steps provided, you can easily control the rasterization behavior of transformed elements when converting your Word documents to different formats. Aspose.Words offers tremendous flexibility and power to work with the transformed elements, allowing you to create converted documents precisely to your specific needs.