---
title: Apply Paragraph Style
linktitle: Apply Paragraph Style
second_title: Aspose.Words Document Processing API
description: Learn how to apply a paragraph style using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/apply-paragraph-style/
---

In this tutorial, we will walk you through how to apply a paragraph style using Aspose.Words for .NET. Follow the steps below to understand the source code and apply the paragraph style.

## Step 1: Creating and configuring the document

To begin, create a new document and an associated DocumentBuilder object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Configuring the paragraph style

We will now configure the paragraph style using the built-in style identifier. Here's how:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Step 3: Add content

We are going to add content to the paragraph. Here's how:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Example source code for Apply Paragraph Style using Aspose.Words for .NET

Here is the complete source code for the Apply Paragraph Style feature with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

With this code you will be able to apply a paragraph style using Aspose.Words for .NET.


