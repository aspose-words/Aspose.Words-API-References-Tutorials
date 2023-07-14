---
title: Add Bidi Marks in Word Document
linktitle: Add Bidi Marks in Word Document
second_title: Aspose.Words Document Processing API
description: Learn to add Bidi marks to a Word document using Aspose.Words for .NET and create professional multilingual documents.
type: docs
weight: 10
url: /net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET is a powerful library for creating, editing, and manipulating Word documents in a C# application. Among the features offered by Aspose.Words is the ability to add Bidi (Bi-directional) marks to a document. In this guide, we will walk you through how to use the C# source code of Aspose.Words for .NET to add Bidi marks to a document.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a popular library that makes Words Processing with Word documents easy and efficient. It offers a wide range of features for creating, editing and manipulating Word documents, including adding Bidi marks.

## Creating the document and adding content

The first step is to create a new document and add content to it. Use the Document class to create a new document instance. Then use the DocumentBuilder class to add text to the document. Here is an example :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

In this example, we create a new document and use the DocumentBuilder to add text. We've added three lines of text: one in English, one in Hebrew, and one in Arabic to demonstrate adding content in different languages.

## Added Bidi marks

Once the content has been added, we can now add Bidi marks to the document. For this, we use the TxtSaveOptions class and we set the AddBidiMarks property to true. Here's how:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

In this example, we create an instance of TxtSaveOptions and set the AddBidiMarks property to true. Next, we use the Save method of the Document class to save the document with Bidi marks.

### Example source code for "Add Bidi Marks" functionality with Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the document and add content
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Add Bidi marks
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Conclusion

In this guide, we have explained how to use Aspose.Words for .NET to add Bidi marks to a Word document using the provided C# source code. By following the provided steps, you can easily add Bidi marks to your Word documents in your C# application. Aspose.Words offers tremendous flexibility and power for Words Processing with text formatting and language management, allowing you to create multilingual documents professionally.

### Frequently Asked Questions

#### Q: What is Aspose.Words for .NET?
Aspose.Words for .NET is a powerful library for creating, editing and manipulating Word documents in a C# application. It offers many features for Words Processing with Word documents, including adding Bidi (bidirectional) marks.

#### Q: What features does Aspose.Words for .NET offer?
Aspose.Words for .NET offers a wide range of features for creating, editing and manipulating Word documents. Some of these features include creating documents, adding content, formatting text, managing tables, merging and splitting documents, converting documents, and more.

#### Q: How can I add Bidi marks to a Word document using Aspose.Words for .NET?
You can add Bidi marks to a Word document by following these steps:

Create a new document using the `Document` class.

Use the `DocumentBuilder` class to add content to the document.

Once you have added the content, use the `TxtSaveOptions` class and set the `AddBidiMarks` property to `true`.

Save the document with Bidi marks using the `Save` method of the `Document` class.

#### Q: Does Aspose.Words support multiple languages for adding Bidi marks?
Yes, Aspose.Words supports multiple languages for adding Bidi marks. You can add Bidi marks to text in different languages, such as English, Hebrew, and Arabic, using Aspose.Words for .NET.

#### Q: Are there any additional options for saving the document with Bidi marks?
Yes, you can specify other options when saving the document with Bidi marks using the `TxtSaveOptions` class. For example, you can set the document save format, encoding options, etc.
