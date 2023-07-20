---
title: Space Between Asian And Latin Text In Word Document
linktitle: Space Between Asian And Latin Text In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to automatically adjust the space between Asian and Latin text in word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/space-between-asian-and-latin-text/
---
In this tutorial, we are going to show you how to use the Space feature between Asian and Latin text in word document feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Creating and configuring the document

To begin, create a new document and an associated DocumentBuilder object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Setting up the space between Asian and Latin text

We will now configure the space between Asian and Latin text using the properties of the ParagraphFormat object. Here's how:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Step 3: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Example source code for Space Between Asian And Latin Text using Aspose.Words for .NET

Here is the complete source code for the Space Between Asian and Latin Text feature with Aspose.Words for .NET:


```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

With this code you will be able to automatically adjust the space between Asian and Latin text in your document using Aspose.Words for .NET.

## Conclusion

In this tutorial, we explored the process of using the Space feature to adjust the spacing between Asian and Latin text in a Word document with Aspose.Words for .NET. By following the outlined steps, you can ensure proper spacing and alignment, particularly helpful when dealing with mixed Asian and Latin content.

### FAQ's

#### Q: What is the Space feature between Asian and Latin text in a Word document?

A: The Space feature between Asian and Latin text in a Word document refers to the ability to automatically adjust the spacing between text written in different scripts, such as Asian (e.g., Chinese, Japanese) and Latin (e.g., English).

#### Q: Why is adjusting space between Asian and Latin text important?

A: Adjusting space between Asian and Latin text is crucial to ensure that different scripts blend harmoniously within the document. Proper spacing enhances readability and overall visual appearance, preventing text from appearing too cramped or spread out.

#### Q: Can I customize the space adjustments between different scripts?

A: Yes, you can customize the space adjustments between different scripts using the `AddSpaceBetweenFarEastAndAlpha` and `AddSpaceBetweenFarEastAndDigit` properties. By enabling or disabling these properties, you can control the space between Asian and Latin text, as well as between Asian text and numbers.

#### Q: Does Aspose.Words for .NET support other document formatting features?

A: Yes, Aspose.Words for .NET offers extensive support for various document formatting features. It includes functionalities for font styles, paragraphs, tables, images, and more. You can effectively manipulate and format your Word documents programmatically.

#### Q: Where can I find additional resources and documentation for Aspose.Words for .NET?

A: For comprehensive resources and documentation on using Aspose.Words for .NET, visit [Aspose.Words API Reference](https://reference.aspose.com/words/net/). There, you will find detailed guides, tutorials, code examples, and API references to help you effectively utilize the powerful features of Aspose.Words for .NET.
