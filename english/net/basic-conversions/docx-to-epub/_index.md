---
title: Docx To Epub
linktitle: Docx To Epub
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert Word documents from Docx to Epub format using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/basic-conversions/docx-to-epub/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a Word document in Docx format to the Epub format. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, you need to initialize the `Document` object by providing the path to your source document in Docx format. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual directory path where your document is located, and `"Document.docx"` with the name of your source document. Here's the code snippet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Step 2: Converting the Document to Epub Format

Next, you can proceed with the conversion process. Call the `Save` method on the `Document` object and provide the path and file name for the output document in Epub format. In this example, we will save it as `"BaseConversions.DocxToEpub.epub"`. Here's the code snippet:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

That's it! You have successfully converted a Word document in Docx format to the Epub format using Aspose.Words for .NET.

### Example source code for Docx To Epub using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

Feel free to use this code in your own projects and modify it according to your specific requirements.