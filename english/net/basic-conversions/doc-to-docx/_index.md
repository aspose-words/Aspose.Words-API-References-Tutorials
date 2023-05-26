---
title: Doc To Docx
linktitle: Doc To Docx
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert Word documents from .doc to Docx format using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/basic-conversions/doc-to-docx/
---

In this tutorial, we will walk you through the step-by-step process of using Aspose.Words for .NET to convert a Word document in .doc format to the Docx format. We will explain the provided C# source code and guide you on how to implement it in your own projects.

To begin, make sure you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Setting up the Development Environment

Before you start coding, ensure that you have a suitable development environment. Open Visual Studio or your preferred C# IDE and create a new project.

## Step 2: Adding References and Importing Namespaces

To use Aspose.Words for .NET, you need to add references to the library in your project. Right-click on the References folder in your project, select "Add Reference," and browse to the location where you installed the Aspose.Words for .NET library. Select the appropriate version and click "OK" to add the reference.

Next, import the necessary namespaces at the top of your C# file:

```csharp
using Aspose.Words;
```

## Step 3: Initializing the Document Object

In this step, you will initialize the `Document` object with the path to your source document in .doc format. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual directory path where your document is located, and `"Document.doc"` with the name of your source document. Here's the code snippet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## Step 4: Converting the Document to Docx Format

Now that you have initialized the `Document` object, you can proceed with the conversion process. Aspose.Words for .NET provides various options and settings for customization, but for a basic conversion, no additional parameters are required.

## Step 5: Saving the Converted Document

To save the converted document in Docx format, you need to call the `Save` method on the `Document` object. Provide the path and file name for the output document. In this example, we will save it as `"BaseConversions.DocToDocx.docx"`. Here's the code snippet:

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

That's it! You have successfully converted a Word document in .doc format to the Docx format using Aspose.Words for .NET.

### Example source code for Doc To Docx using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

Feel free to use this code in your own projects and modify it according to your specific requirements.





