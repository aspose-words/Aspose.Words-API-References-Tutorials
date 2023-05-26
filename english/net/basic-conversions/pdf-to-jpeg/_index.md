---
title: Pdf To Jpeg
linktitle: Pdf To Jpeg
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert PDF documents to JPEG images using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/basic-conversions/pdf-to-jpeg/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a PDF document to JPEG images. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by providing the path to your PDF document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Step 2: Saving the Document as Jpeg Images

Next, save the document as Jpeg images by calling the `Save` method on the `Document` object and providing the path and file name for the output Jpeg images:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");
```

That's it! You have successfully converted a PDF document to Jpeg images using Aspose.Words for .NET.

### Example source code for Pdf To Jpeg using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");

```

Feel free to use this code in your own projects and modify it according to your specific requirements.