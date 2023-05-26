---
title: Load Hyphenation Dictionary For Language
linktitle: Load Hyphenation Dictionary For Language
second_title: Aspose.Words for .NET API Reference
description: Learn how to load a hyphenation dictionary for a specific language in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

In this step-by-step tutorial, we'll show you how to load a hyphenation dictionary for a specific language into Aspose.Words for .NET. We'll explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and configured in your development environment. If you haven't already, download and install the library from the official site.

## Step 1: Loading the document

First, load your document from the specified directory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Step 2: Loading the hyphenation dictionary

Next, open a stream to the hyphenation dictionary file and save it for the desired language. In this example, we load a dictionary for Swiss German (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Make sure you have the appropriate dictionary file in your data directory.

## Step 3: Save the modified document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

So ! You have successfully loaded a hyphenation dictionary for a specific language in Aspose.Words for .NET.

### Example source code for hyphenation dictionary loading for a language using Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Feel free to use this code in your own projects and modify it to suit your specific needs.