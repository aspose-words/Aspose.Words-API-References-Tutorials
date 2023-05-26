---
title: Snap To Grid
linktitle: Snap To Grid
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to explain C# source code of Snap to Grid feature with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/snap-to-grid/
---

In this tutorial, we will walk you through how to use the Snap to Grid feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Creating and configuring the document

To begin, create a new document and an associated DocumentBuilder object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Grid Alignment

Now we'll apply grid alignment to a specific paragraph and the font used in the paragraph. Here's how:

```csharp
// Enable grid alignment for the paragraph
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Write text in the paragraph
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Enable grid alignment for the font used in the paragraph
par.Runs[0].Font.SnapToGrid = true;
```

## Step 3: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Example source code for Snap To Grid using Aspose.Words for .NET

Here is the complete source code for the Snap to Grid feature with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Optimize the layout when typing in Asian characters.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

With this code, you will be able to align your text to the grid and optimize the appearance of your document using Aspose.Words for .NET.


