---
title: Simple Text Find And Replace In Word
linktitle: Simple Text Find And Replace In Word
second_title: Aspose.Words Document Processing API
description: Learn how to perform a simple text find and replace in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/simple-find-replace/
---
In this article, we will explore the C# source code above to understand how to use the Simple Text Find And Replace in word the Aspose.Words for .NET library. This feature allows you to perform simple text replacement by searching for a specific string of characters and replacing it with another string of characters in a Word document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start using simple find and replace, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Step 2: Insert text into the document

Once we have a document, we can insert text using a `DocumentBuilder` object. In our example, we use the `Writeln` method to insert the phrase "Hello _CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Step 3: Simple Text Replacement

We use the `Range.Replace` method to perform simple text replacement. In our example, we replace all occurrences of the string "_ClientName_" with "James Bond" using the `FindReplaceOptions` option with the `FindReplaceDirection.Forward` search direction:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Step 4: Saving the edited document

Finally, we save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Example source code for Simple Find Replace using Aspose.Words for .NET

Here is the full example source code to demonstrate the use of simple search and replace with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Save the modified document
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Conclusion

In this article, we explored the C# source code to understand how to use the Simple Find Replace function of Aspose.Words for .NET. We followed a step-by-step guide to create a document, insert text, perform simple text replacement, and save the edited document.

### FAQ's

#### Q: What is the Simple Text Find And Replace function in Aspose.Words for .NET?

A: The Simple Text Find And Replace feature in Aspose.Words for .NET allows you to perform simple text replacement in a Word document. It allows you to search for a specific character string and replace it with another character string. This can be useful when you want to make global changes to a document, such as replacing names, dates, or other information.

#### Q: How to create a new document in Aspose.Words for .NET?

A: Before using the Simple Text Find And Replace function, you must create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object. Here is a sample code to create a new document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: How to insert text into a document using Aspose.Words for .NET?

A: Once you have a document, you can insert text using a `DocumentBuilder` object. In our example, we use the `Writeln` method to insert the phrase "Hello _CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### Q: How do I perform simple text replacement in a document using Aspose.Words for .NET?

A: To perform a simple text replacement, you can use the `Range.Replace` method. In our example, we replace all occurrences of the string "_ClientName_" with "James Bond" using the `FindReplaceOptions` option with the `FindReplaceDirection.Forward` search direction:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Q: How to save edited document in Aspose.Words for .NET?

A: Once you have done the text replacement, you can save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```
