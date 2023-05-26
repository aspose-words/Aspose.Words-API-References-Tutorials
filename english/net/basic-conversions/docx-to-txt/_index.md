---
title: Docx To Txt
linktitle: Docx To Txt
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert Word documents from Docx to plain text (Txt) using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/basic-conversions/docx-to-txt/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a Word document in Docx format to plain text (Txt). We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object with the path to your source document in Docx format:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Step 2: Saving the Document in Txt Format

Next, save the document in plain text (Txt) format by calling the `Save` method on the `Document` object and providing the path and file name for the output Txt document:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

That's it! You have successfully converted a Word document in Docx format to plain text (Txt) using Aspose.Words for .NET.

### Example source code for Docx To Txt using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

Feel free to use this code in your own projects and modify it according to your specific requirements.