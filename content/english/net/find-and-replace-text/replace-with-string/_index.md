---
title: Replace With String
linktitle: Replace With String
second_title: Aspose.Words Document Processing API
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

### FAQ's

#### Q: What is the "Replace With String" function in Aspose.Words for .NET?

A: The "Replace With String" function in Aspose.Words for .NET allows you to perform text replacement based on a specific character string in a Word document. It enables you to find occurrences of a particular string and replace them with another specified string.

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

#### Q: How can I perform text replacement with a string in Aspose.Words for .NET?

A: To perform text replacement with a string in Aspose.Words for .NET, you can use the `Range.Replace` method and specify the string to be replaced and the string to replace it with. This method performs a simple text match and replaces all occurrences of the specified string. Here's an example:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Q: Can I perform case-sensitive text replacement with the "Replace With String" function in Aspose.Words for .NET?

A: Yes, by default, the "Replace With String" function in Aspose.Words for .NET is case-sensitive. This means that it will only replace text that exactly matches the specified string in terms of case. If you want to perform case-insensitive replacement, you can modify the text to be replaced and the replacement string to have the same case, or you can use other techniques such as regular expressions.

#### Q: Can I replace multiple occurrences of a string in a document using the "Replace With String" function in Aspose.Words for .NET?

A: Yes, you can replace multiple occurrences of a string in a document using the "Replace With String" function in Aspose.Words for .NET. The `Range.Replace` method will replace all occurrences of the specified string in the document's content.

#### Q: Are there any limitations or considerations when using the "Replace With String" function in Aspose.Words for .NET?

A: When using the "Replace With String" function in Aspose.Words for .NET, it's important to be aware of the context and ensure that the replacement is applied only where intended. Make sure that the search string doesn't appear in unwanted places, such as within other words or as part of special formatting. Additionally, consider performance implications when Words Processing with large documents or frequent replacements.

#### Q: Can I replace strings with different lengths using the "Replace With String" function in Aspose.Words for .NET?

A: Yes, you can replace strings with different lengths using the "Replace With String" function in Aspose.Words for .NET. The replacement string can be of any length, and it will replace the exact match of the search string. The document will adjust accordingly to accommodate the new string length.
