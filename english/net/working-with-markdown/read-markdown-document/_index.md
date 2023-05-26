---
title: Read Markdown Document
linktitle: Read Markdown Document
second_title: Aspose.Words for .NET API Reference
description: Learn how to read markdown document with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/read-markdown-document/
---

In this example, we will walk you through how to read a Markdown document using Aspose.Words for .NET Markdown is a lightweight markup language used to format plain text.

## Step 1: Reading the Markdown document

First, we'll use the `Document` class to read the Markdown document. We need to specify the path of the Markdown file to read.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");
```

## Step 2: Remove header formatting

We can remove the formatting from the header in the last paragraph of the document. In this example, we assign the "Quote" style to the paragraph.

```csharp
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];
```

## Step 3: Saving the document

Finally, we can save the document in the desired format.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

### Example source code for reading a Markdown document with Aspose.Words for .NET


```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Quotes.md");

	// Let's remove Heading formatting from a Quote in the very last paragraph.
	Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
	paragraph.ParagraphFormat.Style = doc.Styles["Quote"];

	doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
            
```

Congratulation ! You have now learned how to read a Markdown document with Aspose.Words for .NET.


