---
title: Hyphenate Words Of Languages
linktitle: Hyphenate Words Of Languages
second_title: Aspose.Words for .NET API Reference
description: Learn how to hyphenate words in different languages in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-hyphenation/hyphenate-words-of-languages/
---

In this step-by-step tutorial, we will guide you on how to hyphenate words in different languages in Word documents using Aspose.Words for .NET. We'll explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and configured in your development environment. If you haven't already, download and install the library from the official site.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by specifying the path to your source document containing text in different languages:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Step 2: Saving Hyphenation Dictionaries

Next, save the hyphenation dictionaries for the different languages you want to process. In this example, we register dictionaries for American English and Swiss German:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Make sure you have the appropriate dictionary files in your data directory.

## Step 3: Processing words by hyphenation

Now you can use hyphenation features to process words in different languages. You can use different methods of `Document` or `DocumentBuilder` depending on your specific needs.

```csharp
// Example: Using the Hyphenate method of DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Step 4: Save the document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

So ! You have successfully processed words by hyphenating them in different languages in a Word document using Aspose.Words for .NET.

### Sample source code for word hyphenation using Aspose.Words for .NET

	```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "German text.docx");

	Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
	Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

	doc.Save(dataDir + "TreatmentByCesure.pdf");
	```

Feel free to use this code in your own projects and modify it to suit your specific needs.

