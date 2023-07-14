---
title: Load Chm
linktitle: Load Chm
second_title: Aspose.Words Document Processing API
description: Learn how to load CHM files with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/load-chm/
---

When Words Processing with HTML Help (CHM) files in a C# application, it's important to be able to load them correctly. With the Aspose.Words library for .NET, you can easily load CHM files using the appropriate load options. In this step-by-step guide, we will show you how to use Aspose.Words for .NET C# source code to load a CHM file using the LoadOptions load options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Configuring loading options

The first step is to configure the load options for our CHM file. Use the LoadOptions class to specify loading parameters. In our case, we need to set the Encoding property to the appropriate encoding for CHM files, typically "windows-1251". Here's how to do it:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

We create a new LoadOptions object and set the Encoding property to "windows-1251" encoding for CHM files.

## Loading CHM file

Now that we have configured the load options, we can load the CHM file using the Document class and specify the load options. Here is an example :

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

In this example, we load the CHM file "HTML help.chm" located in the documents directory using the load options specified.

### Example source code for LoadOptions with "Load Chm" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configuration of the loading options with the "Load Chm" feature
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// Load the CHM file with the specified options
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## Conclusion

In this guide, we explained how to load a CHM file using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Loading CHM files correctly is essential to be able to manipulate and convert them efficiently with Aspose.Words.
