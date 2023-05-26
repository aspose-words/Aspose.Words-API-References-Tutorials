---
title: Ranges Get Text
linktitle: Ranges Get Text
second_title: Aspose.Words for .NET API Reference
description: Learn how to easily extract text from a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-ranges/ranges-get-text/
---

Aspose.Words for .NET is a powerful library for creating, editing, and manipulating Word documents in a C# application. Among the features offered by Aspose.Words is the ability to get the text contained in specific ranges of a document. In this guide, we will walk you through how to use the C# source code of Aspose.Words for .NET to extract text from a Word document.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a popular library that makes working with Word documents easy and efficient. It offers a wide range of features for creating, editing and manipulating Word documents, including extracting text from specific ranges.

## Loading the Word document

The first step is to load the Word document from which you want to extract the text. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In this example, we load the document "Document.docx" located in the documents directory.

## Extracting text from a specific range

Once the document is loaded, you can access the different ranges of the document and extract the desired text. In this example, we will extract all text from the document. Here's how:

```csharp
string text = doc.Range.Text;
```

In this example, we use the Range property of the Document class to access the full range of the document. Then we use the Text property to get the text contained in that range.

## Display of extracted text

Now that we have extracted the text from the specified range, we can display or process it as needed by your application. For example, you can display it on screen or save it to an output file. Here is an example to display the extracted text:

```csharp
Console.WriteLine(text);
```

In this example, we use the WriteLine method of the Console class to display the extracted text in the console.

### Example source code for "Get text from ranges" feature with Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the Word document
Document doc = new Document(dataDir + "Document.docx");

// Extract the text from the document
string text = doc.Range.Text;

// Display the extracted text
Console.WriteLine(text);
```

## Conclusion

In this guide, we have covered how to use Aspose.Words for .NET to extract text from a Word document using the provided C# source code. By following the steps provided, you can easily extract text from specific ranges in your Word documents in your C# application. Aspose.Words offers tremendous flexibility and power for working with document content, allowing you to process and use text according to your specific needs.