---
title: Txt To Docx
linktitle: Txt To Docx
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert plain text files (Txt) to Word documents (Docx) using Aspose.Words for .NET. Step-by-step tutorial with example code.
type: docs
weight: 10
url: /net/basic-conversions/txt-to-docx/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a plain text file (Txt) to a Word document in Docx format. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by providing the path to your plain text file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Step 2: Saving the Document in Docx Format

Next, save the document in the Docx format by calling the `Save` method on the `Document` object and providing the path and file name for the output Docx document:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

That's it! You have successfully converted a plain text file (Txt) to a Word document in Docx format using Aspose.Words for .NET.

### Example source code for Txt To Docx using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// The encoding of the text file is automatically detected.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

Feel free to use this code in your own projects and modify it according to your specific requirements.
