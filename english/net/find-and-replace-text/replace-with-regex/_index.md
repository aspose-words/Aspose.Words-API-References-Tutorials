---
title: Replace With Regex
linktitle: Replace With Regex
second_title: Aspose.Words Document Processing API
description: Learn how to perform regular expression based text replacement in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/replace-with-regex/
---

In this article, we will explore the C# source code above to understand how to use the Replace With Regex function in the Aspose.Words for .NET library. This feature allows you to perform text replacement based on specific patterns defined by a regular expression.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start using regular expression replacement, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

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

## Step 3: Configuring Find and Replace Options

Now we will configure find and replace options using a `FindReplaceOptions` object. In our example, we use the default options:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## Step 4: Replace with regular expression

We use the `Range.Replace` method to perform text replacement using a regular expression. In our example, we use the regular expression "[s|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Step 5: Saving the modified document

Finally, we save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Example source code for Replace With Regex using Aspose.Words for .NET

Here is the full sample source code to demonstrate the use of regular expression replacement with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Replace With Regex function of Aspose.Words for .NET. We followed a step-by-step guide to create a document, insert text, perform the replacement with a regular expression and save the modified document.

