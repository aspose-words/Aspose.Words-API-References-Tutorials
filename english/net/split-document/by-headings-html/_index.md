---
title: By Headings Html
linktitle: By Headings Html
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to explain the C# source code of the By Heading HTML feature of Aspose.Words for .NET
type: docs
weight: 10
url: /net/split-document/by-headings-html/
---
In this tutorial, we will walk you through how to split a Word document into smaller parts using the By HTML Heading feature of Aspose.Words for .NET. Follow the steps below to understand the source code and generate separate HTML documents based on Heading.

## Step 1: Loading the document

To get started, specify the directory for your document and load the document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Step 2: Dividing the document by Heading in HTML format

Now we will set save options to split the document into smaller parts based on Heading in HTML format. Here's how:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Split the document into smaller parts, in this case separating it by title.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Example source code for By Headings HTML using Aspose.Words for .NET

Here is the complete source code for the By HTML Heading feature of Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Split a document into smaller parts, in this instance split by heading.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

With this code, you will be able to split a Word document into smaller parts using Aspose.Words for .NET, based on headings. You can then generate separate HTML documents for each part.


