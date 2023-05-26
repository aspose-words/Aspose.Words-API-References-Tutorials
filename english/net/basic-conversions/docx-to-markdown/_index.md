---
title: Docx To Markdown
linktitle: Docx To Markdown
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert Word documents from Docx to Markdown format using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/basic-conversions/docx-to-markdown/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a Word document in Docx format to Markdown. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document and DocumentBuilder Objects

First, initialize the `Document` object and the `DocumentBuilder` object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Adding Content to the Document

Next, use the `DocumentBuilder` object to add content to the document. In this example, we will add a simple text paragraph using the `Writeln` method:

```csharp
builder.Writeln("Some text!");
```

Feel free to add more complex content such as headings, tables, lists, or formatting as needed.

## Step 3: Saving the Document in Markdown Format

To save the document in Markdown format, use the `Save` method on the `Document` object and provide the path and file name for the output document. In this example, we will save it as `"BaseConversions.DocxToMarkdown.md"`:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");
```

That's it! You have successfully converted a Word document in Docx format to Markdown using Aspose.Words for .NET.

### Example source code for Docx To Markdown using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Some text!");

	doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");

```

Feel free to use this code in your own projects and modify it according to your specific requirements.