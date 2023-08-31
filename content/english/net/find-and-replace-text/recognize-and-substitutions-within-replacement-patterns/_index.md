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

### FAQ's

#### Q: What is the "Recognize And Substitutions Within Replacement Patterns" feature in Aspose.Words for .NET?

A: The "Recognize And Substitutions Within Replacement Patterns" feature in Aspose.Words for .NET allows you to recognize complex search patterns using regular expressions and perform substitutions based on the captured groups during document manipulation. It enables you to transform the matched text dynamically by referencing the captured groups in the replacement pattern.

#### Q: How can I create a new document using Aspose.Words for .NET?

A: To create a new document using Aspose.Words for .NET, you can instantiate a `Document` object. Here's an example of C# code to create a new document:

```csharp
Document doc = new Document();
```

#### Q: How can I insert text into a document using Aspose.Words for .NET?

A: Once you have a document, you can insert text using a `DocumentBuilder` object. For example, to insert the phrase "Jason gives money to Paul.", you can use the `Write` method:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### Q: How can I perform text search and replace using regular expressions in Aspose.Words for .NET?

A: To perform text search and replace using regular expressions in Aspose.Words for .NET, you can use the `Range.Replace` function along with a regular expression pattern. You can create a `Regex` object with the desired pattern and pass it to the `Replace` method:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: How can I use captured groups in the replacement pattern during text search and replace in Aspose.Words for .NET?

A: To use captured groups in the replacement pattern during text search and replace in Aspose.Words for .NET, you can enable the `UseSubstitutions` property of the `FindReplaceOptions` object. This allows you to reference the captured groups using `$1`, `$2`, etc. in the replacement pattern:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: What does the example source code demonstrate for the "Recognize And Substitutions Within Replacement Patterns" feature in Aspose.Words for .NET?

A: The example source code demonstrates the use of the "Recognize And Substitutions Within Replacement Patterns" feature in Aspose.Words for .NET. It shows how to create a document, insert text, perform text search and replace using regular expressions, and use captured groups in the replacement pattern to transform the matched text dynamically.

#### Q: Where can I find more information and examples on using regular expressions in Aspose.Words for .NET?

A: For more information and examples on using regular expressions in Aspose.Words for .NET, you can refer to the [Aspose.Words for .NET API references](https://reference.aspose.com/words/net/). The documentation provides detailed explanations and code examples for various scenarios involving regular expressions and text manipulation in Aspose.Words for .NET.

#### Q: Can I manipulate other aspects of the document based on the captured groups during text search and replace?

A: Yes, you can manipulate other aspects of the document based on the captured groups during text search and replace. In addition to performing text substitutions, you can modify formatting, styles, document structure, and other elements based on the captured groups using the various APIs provided by Aspose.Words for .NET.

#### Q: Are there any limitations or considerations when using regular expressions and captured groups in Aspose.Words for .NET?

A: While regular expressions and captured groups offer powerful capabilities for text search and replace in Aspose.Words for .NET, it's important to consider the complexity and performance implications. Highly complex regular expressions and a large number of captured groups can impact performance. It's recommended to test and optimize regular expressions for your specific use cases to ensure efficient document manipulation.

#### Q: Can I use the "Recognize And Substitutions Within Replacement Patterns" feature with languages other than English?

A: Yes, the "Recognize And Substitutions Within Replacement Patterns" feature in Aspose.Words for .NET can be used with languages other than English. Regular expressions are language-agnostic and can be crafted to match specific patterns in any language. You can adjust the regular expression pattern to suit your desired language and the specific text patterns you want to recognize and substitute.
