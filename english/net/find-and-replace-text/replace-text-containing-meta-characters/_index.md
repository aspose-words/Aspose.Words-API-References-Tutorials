---
title: Word Replace Text Containing Meta Characters
linktitle: Word Replace Text Containing Meta Characters
second_title: Aspose.Words Document Processing API
description: Learn how to word replace text containing metacharacters in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/replace-text-containing-meta-characters/
---
In this article, we will explore the above C# source code to understand how to use Word Replace Text Containing Meta Characters function in Aspose.Words for .NET library. This feature allows you to replace portions of text in a document containing specific meta-characters.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start using metacharacter text replacement, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Step 2: Insert text into the document

Once we have a document, we can insert text using a `DocumentBuilder` object. In our example, we use the `Writeln` method to insert multiple paragraphs of text into different sections:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## Step 3: Configuring Find and Replace Options

Now we will configure find and replace options using a `FindReplaceOptions` object. In our example, we set the alignment of the replaced paragraphs to "Centered":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## Step 4: Replacing Text Containing Metacharacters

We use the `Range.Replace` method to perform the replacement of text containing metacharacters. In our example, we replace each occurrence of the word "section" followed by a paragraph break with the same word followed by several dashes and a new paragraph break:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Step 5: Replacing a custom text tag

We also use the `Range.Replace` method to replace a custom "{insert-section}" text tag with a section break. In our example, we replace "{insert-section}" with "&b" to insert a section break:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Step 6: Saving the edited document

Finally, we save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Example source code for Replace Text Containing Meta Characters using Aspose.Words for .NET

Here is the full example source code to demonstrate the use of text replacement containing metacharacters with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// Double each paragraph break after word "section", add kind of underline and make it centered.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Insert section break instead of custom text tag.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Replace Text Containing Meta Characters feature of Aspose.Words for .NET. We followed a step-by-step guide to create a document, insert text, replace text containing metacharacters, and save the modified document.

### FAQ's

#### Q: What is the Replace Text Containing Meta Characters function in Aspose.Words for .NET?

A: The Replace Text Containing Meta Characters feature in Aspose.Words for .NET allows you to replace portions of text in a document containing specific meta characters. You can use this feature to perform advanced replacements in your document taking metacharacters into account.

#### Q: How to create a new document in Aspose.Words for .NET?

A: Before using the Replace Text Containing Meta Characters function, you must create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object. Here is a sample code to create a new document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: How to insert text into a document using Aspose.Words for .NET?

A: Once you have a document, you can insert text using a `DocumentBuilder` object. In our example, we use the `Writeln` method to insert multiple paragraphs of text into different sections:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### Q: How to configure search and replace options in Aspose.Words for .NET?

A: Now we will configure find and replace options using a `FindReplaceOptions` object. In our example, we set the alignment of the replaced paragraphs to "Centered":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### Q: How to replace text containing metacharacters in a document using Aspose.Words for .NET?

A: We use the `Range.Replace` method to perform the replacement of text containing meta-characters. In our example, we replace each occurrence of the word "section" followed by a paragraph break with the same word followed by several dashes and a new paragraph break:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### Q: How to replace a custom text tag containing meta characters in a document using Aspose.Words for .NET?

A: We also use the `Range.Replace` method to replace a custom "{insert-section}" text tag with a section break. In our example, we replace "{insert-section}" with "&b" to insert a section break:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### Q: How to save edited document in Aspose.Words for .NET?

A: Once you have made changes to the document, you can save it to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```
