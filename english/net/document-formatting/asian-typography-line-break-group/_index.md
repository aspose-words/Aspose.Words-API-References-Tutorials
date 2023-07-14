---
title: Asian Typography Line Break Group
linktitle: Asian Typography Line Break Group
second_title: Aspose.Words Document Processing API
description: Learn how to use Asian Typography line break group with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/asian-typography-line-break-group/
---

In this tutorial, we are going to show you how to use Asian Typography line break group feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply formatting changes.

## Step 1: Loading the document

To get started, specify the directory for your documents and load the document containing the Asian typography into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Step 2: Asian Typography Setup

We will now configure the Asian typography settings for the first paragraph of the document. Here's how:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Step 3: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Example source code for Asian Typography Line Break Group using Aspose.Words for .NET

Here is the complete source code for Asian Typography Line Break Group feature with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
With this code you will be able to apply Asian Typography line break group using Aspose.Words for .NET.


