---
title: Meta Characters In Search Pattern
linktitle: Meta Characters In Search Pattern
second_title: Aspose.Words Document Processing API
description: Learn how to use metacharacters in the search pattern with Aspose.Words for .NET to manipulate Word documents.
type: docs
weight: 10
url: /net/find-and-replace-text/meta-characters-in-search-pattern/
---

In this article, we will explore the above C# source code to understand how to use Meta Characters In Search Pattern function in Aspose.Words for .NET library. This feature allows you to use special metacharacters to perform advanced searches and replaces in Word documents.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start using metacharacters in the search pattern, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Step 2: Insert text into the document

Once we have a document, we can insert text using a `DocumentBuilder` object. In our example, we use the `Writeln` and `Write` methods to insert two lines of text:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Step 3: Find and replace text with metacharacters

Now we will use the `Range.Replace` function to search and replace text using a search pattern containing special metacharacters. In our example, we replace the phrase "This is line 1&pThis is line 2" with "This line is replaced" using the `&p` metacharacter to represent a paragraph break:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Step 4: Inserting a page break in the document

To illustrate the use of another metacharacter, we will insert a page break into the document using the `InsertBreak` method with the `BreakType.PageBreak` parameter. We first move the cursor from the `DocumentBuilder` to the end of the document, then we insert the page break and a new line of text:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Step 5: Find and replace with another metacharacter

Now we'll perform another search and replace using the `&m` metacharacter to represent a page break. We replace the phrase "This is line 1&mThis is line 2" with "The page break is replaced with new text." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Step 6: Saving the edited document

Finally, we save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Example source code for Meta Characters In Search Pattern using Aspose.Words for .NET

Here is the full sample source code to demonstrate the use of metacharacters in the search pattern with Aspose.Words for .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Conclusion

In this article, we explored the C# source code to understand how to use metacharacters in the search pattern of Aspose.Words for .NET. We followed a step-by-step guide to create a document, insert text, perform search and replace using special metacharacters, insert page breaks, and save the edited document.

