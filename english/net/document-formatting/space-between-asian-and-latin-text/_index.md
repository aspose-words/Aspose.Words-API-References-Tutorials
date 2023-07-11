---
title: Space Between Asian And Latin Text
linktitle: Space Between Asian And Latin Text
second_title: Aspose.Words Document Processing API
description: Learn how to automatically adjust the space between Asian and Latin text in your document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/space-between-asian-and-latin-text/
---

In this tutorial, we are going to show you how to use the Space feature between Asian and Latin text with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Creating and configuring the document

To begin, create a new document and an associated DocumentBuilder object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Setting up the space between Asian and Latin text

We will now configure the space between Asian and Latin text using the properties of the ParagraphFormat object. Here's how:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Step 3: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Example source code for Space Between Asian And Latin Text using Aspose.Words for .NET

Here is the complete source code for the Space Between Asian and Latin Text feature with Aspose.Words for .NET:


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

With this code you will be able to automatically adjust the space between Asian and Latin text in your document using Aspose.Words for .NET.




