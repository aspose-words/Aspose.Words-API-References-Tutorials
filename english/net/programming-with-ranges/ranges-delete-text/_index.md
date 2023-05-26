---
title: Ranges Delete Text
linktitle: Ranges Delete Text
second_title: Aspose.Words for .NET API Reference
description: Learn how to delete text in specific ranges in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-ranges/ranges-delete-text/
---

Aspose.Words for .NET is a powerful library for creating, editing, and manipulating Word documents in a C# application. Among the features offered by Aspose.Words is the ability to delete specific text within defined ranges of a document. In this guide, we will walk you through how to use the C# source code of Aspose.Words for .NET to delete text in specific ranges in a Word document.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a popular library that makes working with Word documents easy and efficient. It offers a wide range of features for creating, editing, and manipulating Word documents, including deleting text in specific ranges.

## Loading the Word document

The first step is to load the Word document where you want to delete text. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In this example, we load the document "Document.docx" located in the documents directory.

## Deleting text in specific ranges

Once the document is loaded, you can navigate to sections of the document and specify the ranges where you want to delete text. In this example, we will remove all text from the first section of the document. Here's how:

```csharp
doc.Sections[0].Range.Delete();
```

In this example, we are accessing the first section of the document using index 0 (sections are indexed from 0). Next, we call the Delete method on the section range to delete all text from that range.

## Save modified document

Once you have deleted the text in the specified ranges, you can save the modified document using the Save method of the Document class. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithRangesDeleteText.ModifiedDocument.docx");
```

In this example, we save the modified document as "WorkingWithRangesDeleteText.ModifiedDocument.docx".

### Example source code for "Delete text in ranges" functionality with Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the Word document
Document doc = new Document(dataDir + "Document.docx");

// Delete the text in the first section of the document
doc.Sections[0].Range.Delete();

// Save the modified document
doc.Save(dataDir + "WorkingWithRangesDeleteText.ModifiedDocument.docx");
```

## Conclusion

In this guide, we have covered how to use Aspose.Words for .NET to delete text in specific ranges of a Word document using the provided C# source code. By following the steps provided, you can easily delete text in defined ranges in your Word documents in your C# application. Aspose.Words offers tremendous flexibility and power for working with ranges of text, allowing you to create and edit Word documents precisely and purposefully.
