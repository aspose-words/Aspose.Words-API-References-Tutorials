---
title: Replace With String
linktitle: Replace With String
second_title: Aspose.Words for .NET API Reference
description: Learn how to replace text with a string in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/replace-with-string/
---

In this article, we will explore the C# source code above to understand how to use the Replace With String function in the Aspose.Words for .NET library. This feature allows you to perform text replacement based on a specific character string in a Word document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start using string replacement, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Step 2: Insert text into the document

Once we have a document, we can insert text using a `DocumentBuilder` object. In our example, we use the `Writeln` method to insert the phrase "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Step 3: Replace with a string

We use the `Range.Replace` method to replace text with a string. In our example, we replace all occurrences of the word "sad" with "bad" using the `FindReplaceOptions` option with the `FindReplaceDirection.Forward` search direction:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Step 4: Saving the edited document

Finally, we save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Example source code for Replace With String using Aspose.Words for .NET

Here is the full sample source code to illustrate the use of replacing with a character string with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Replace With String function of Aspose.Words for .NET. We followed a step-by-step guide to create a document, insert text, replace with a string and save the modified document.

