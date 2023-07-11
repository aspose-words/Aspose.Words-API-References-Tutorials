---
title: Load With Encoding
linktitle: Load With Encoding
second_title: Aspose.Words Document Processing API
description: Learn how to load a document with a specified encoding using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/load-with-encoding/
---
When working with text documents in a C# application, it is important to be able to load them correctly by specifying the correct encoding. With the Aspose.Words library for .NET, you can easily load text documents with the desired encoding using the LoadOptions load options. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to load a text document with the specified encoding using the LoadOptions load options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Configuring loading options

The first step is to configure the loading options for our text document. Use the LoadOptions class to specify loading parameters. In our case, we need to set the Encoding property to the desired encoding, for example, Encoding.UTF7 for UTF-7 encoding. Here's how to do it:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };
```

We create a new LoadOptions object and set the Encoding property to Encoding.UTF7 to specify UTF-7 encoding.

## Loading document with specified encoding

Now that we have configured the load options, we can load the document using the Document class and specify the load options. Here is an example :

```csharp
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

In this example, we load the document "Encoded in UTF-7.txt" located in the documents directory using the load options specified.

### Sample source code for LoadOptions with "Load With Encoding" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure loading options with the desired encoding (UTF-7)
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };

// Load the document with the specified encoding
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

## Conclusion

In this guide, we explained how to load a text document with a specified encoding using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Loading text documents with the proper encoding ensures correct and accurate reading of content in your application.