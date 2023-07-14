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

### FAQ's

#### Q: What is the "Replace With Regex" function in Aspose.Words for .NET?

A: The "Replace With Regex" function in Aspose.Words for .NET allows you to perform text replacement based on specific patterns defined by a regular expression. It enables you to find and replace text in a document by specifying complex search patterns using regular expressions.

#### Q: How can I create a new document using Aspose.Words for .NET?

A: To create a new document using Aspose.Words for .NET, you can instantiate a `Document` object. Here's an example of C# code to create a new document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### Q: How can I insert text into a document using Aspose.Words for .NET?

A: Once you have a document, you can insert text using a `DocumentBuilder` object. In Aspose.Words for .NET, you can use various methods of the `DocumentBuilder` class to insert text at different locations. For example, you can use the `Writeln` method to insert text on a new line. Here's an example:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### Q: What are the Find and Replace options in Aspose.Words for .NET?

A: Find and Replace options in Aspose. Words for .NET allow you to configure how the search and replace operation should be performed. Some commonly used options include `MatchCase` (to specify whether the search is case-sensitive or not), `FindWholeWordsOnly` (to match whole words only), and `Direction` (to specify the search direction). You can customize these options based on your specific requirements.

#### Q: How can I perform text replacement using a regular expression in Aspose.Words for .NET?

A: To perform text replacement using a regular expression in Aspose.Words for .NET, you can use the `Range.Replace` method and pass a `Regex` object as the search pattern. This allows you to define complex search patterns using regular expressions. Here's an example:

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

#### Q: Can I replace text with different content based on the matched pattern using regular expressions in Aspose.Words for .NET?

A: Yes, you can replace text with different content based on the matched pattern using regular expressions in Aspose.Words for .NET. By capturing groups in your regular expression pattern, you can reference and use the captured groups in the replacement string. This allows for dynamic substitutions based on the matched pattern.

#### Q: Are there any limitations or considerations when using regular expressions for text replacement in Aspose.Words for .NET?

A: When using regular expressions for text replacement in Aspose.Words for .NET, it's important to be mindful of the complexity and performance implications. Regular expressions can be powerful, but complex patterns may impact the performance of the search and replace operation. Additionally, ensure that your regular expressions are accurate and account for any edge cases or potential conflicts with the document's content.

#### Q: Can I perform case-insensitive text replacement using regular expressions in Aspose.Words for .NET?

A: Yes, you can perform case-insensitive text replacement using regular expressions in Aspose.Words for .NET. By default, regular expressions in .NET are case-sensitive. However, you can modify the behavior by using the appropriate RegexOptions.IgnoreCase flag when constructing your Regex object.

#### Q: Can I replace text in multiple documents using the "Replace With Regex" function in Aspose.Words for .NET?

A: Yes, you can replace text in multiple documents using the "Replace With Regex" function in Aspose.Words for .NET. Simply repeat the steps for each document you want to process. Load each document, perform the text replacement using the specified regular expression, and save the modified document. You can automate this process for multiple documents within a loop or by iterating over a list of document file paths.
