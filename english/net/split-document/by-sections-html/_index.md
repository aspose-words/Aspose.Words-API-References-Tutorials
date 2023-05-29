---
title: By Sections Html
linktitle: By Sections Html
second_title: Aspose.Words for .NET API Reference
description: Learn how to split a Word document into by sections Html using Aspose.Words for .NET with complete code example.
type: docs
weight: 10
url: /net/split-document/by-sections-html/
---

In this example, we will show you how to split a Word document into separate sections in HTML format using the By HTML Sections feature of Aspose.Words for .NET. Follow the steps below to understand the source code and generate separate HTML documents for each section.

## Step 1: Loading the document

To get started, specify the directory for your document and load the document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Step 2: Dividing the document into sections in HTML format

Now we will set the save options to divide the document into sections in HTML format. Here's how to do it:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Example source code for By Sections HTML using Aspose.Words for .NET

Here is the complete source code for the By HTML Sections feature of Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

With this code you will be able to split a Word document into separate sections in HTML format using Aspose.Words for .NET.

Now you can generate separate HTML documents for each section of the initial document.




