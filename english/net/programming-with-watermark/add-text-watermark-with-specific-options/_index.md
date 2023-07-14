---
title: Add Text Watermark With Specific Options
linktitle: Add Text Watermark With Specific Options
second_title: Aspose.Words Document Processing API
description: Learn how to add a text watermark with specific options using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/programming-with-watermark/add-text-watermark-with-specific-options/
---

In this tutorial, we will walk you through how to add a text watermark with specific options using Aspose.Words for .NET. A text watermark is text superimposed on a document to indicate that it is a draft, confidential, etc.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Loading the document

We will load an existing document using the document path.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Step 3: Add text watermark with specific options

We will create an instance of the `TextWatermarkOptions` class and set the desired options for the text watermark.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Step 4: Save the document

Finally, we can save the document with the added text watermark.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Example source code for adding text watermark with specific options with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Congratulation ! You have now learned how to add text watermark with specific options using Aspose.Words for .NET.


