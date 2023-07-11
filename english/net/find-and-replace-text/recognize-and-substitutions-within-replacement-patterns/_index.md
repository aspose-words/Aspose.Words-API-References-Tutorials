---
title: Recognize And Substitutions Within Replacement Patterns
linktitle: Recognize And Substitutions Within Replacement Patterns
second_title: Aspose.Words Document Processing API
description: Learn how to use replacement patterns with recognitions and substitutions in Aspose.Words for .NET to manipulate Word documents.
type: docs
weight: 10
url: /net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

In this article, we will explore the above C# source code to understand how to use Recognize And Substitutions Within Replacement Patterns function in Aspose.Words for .NET library. This feature helps recognize complex search patterns and perform substitutions based on groups captured during document manipulation.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start using matches and substitutions in replacement patterns, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

```csharp
Document doc = new Document();
```

## Step 2: Insert text into the document

Once we have a document, we can insert text using a `DocumentBuilder` object. In our example, we're using the `Write` method to insert the phrase "Jason gives Paul some money." :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Step 3: Recognitions and Substitutions in Replacement Patterns

Now we will use the `Range.Replace` function to perform text search and replace using a regular expression to recognize specific patterns. In our example, we use the regular expression `([A-z]+) gives money to ([A-z]+)` to recognize sentences where someone gives money to someone else . We use the replacement pattern `$2 takes money from $1` to perform the substitution by reversing the roles. The use of `$1` and `$2` refers to the groups captured by the regular expression:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Example source code for Recognize And Substitutions Within Replacement Patterns using Aspose.Words for .NET

Here is the full example source code to illustrate the use of matches and substitutions in replacement patterns with Aspose.Words for .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Conclusion

In this article, we explored the C# source code to understand how to use the Recognize And Substitutions Within Replacement Patterns feature of Aspose.Words for .NET. We followed a step-by-step guide to create a document, insert text, perform search and replace using regular expressions and substitution patterns based on captured groups, and manipulate the document.

