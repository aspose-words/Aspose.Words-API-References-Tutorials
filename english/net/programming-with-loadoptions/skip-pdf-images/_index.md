---
title: Skip Pdf Images
linktitle: Skip Pdf Images
second_title: Aspose.Words Document Processing API
description: Learn how to load a PDF document skipping loading PDF images with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-loadoptions/skip-pdf-images/
---

When working with PDF documents in a C# application, it may be necessary to skip loading PDF images for performance or storage space management reasons. With the Aspose.Words library for .NET, you can easily skip loading PDF images using the PdfLoadOptions load options. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to load a PDF document by skipping the loading of PDF images using the PdfLoadOptions load options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Configuring loading options

The first step is to configure the loading options for our PDF document. Use the PdfLoadOptions class to specify load parameters. In our case, we need to set the SkipPdfImages property to true to skip loading PDF images. Here's how to do it:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };
```

We create a new PdfLoadOptions object and set the SkipPdfImages property to true to skip loading PDF images.

## Load PDF document skipping PDF images

Now that we have configured the loading options, we can load the PDF document using the Document class and specify the loading options. Here is an example :

```csharp
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

In this example, we are loading the PDF document "Pdf Document.pdf" located in the documents directory using the specified load options.

### Example source code for PdfLoadOptions with "Skip Pdf Images" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure loading options with the "Skip Pdf Images" feature
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };

// Load the PDF document skipping the PDF images
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

## Conclusion

In this guide, we explained how to load a PDF document skipping the loading of PDF images using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Skipping PDF image loading can improve performance and storage space management when processing PDF documents.
