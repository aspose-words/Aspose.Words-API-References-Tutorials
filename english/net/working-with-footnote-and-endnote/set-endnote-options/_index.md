---
title: Set Endnote Options
linktitle: Set Endnote Options
second_title: Aspose.Words for .NET API Reference
description: Learn how to set endnote options in Word documents using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/working-with-footnote-and-endnote/set-endnote-options/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to set endnote options in a Word document. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by providing the path to your source document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Step 2: Initializing the DocumentBuilder Object

Next, initialize the `DocumentBuilder` object to perform operations on the document:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Adding Text and Endnote

Use the `Write` method of the `DocumentBuilder` object to add text to the document, and the `InsertFootnote` method to insert an endnote:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Step 4: Setting Endnote Options

Access the `EndnoteOptions` property of the document to modify endnote options. In this example, we set the restart rule to restart on each page and the position to the end of the section:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Step 5: Saving the Document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

That's it! You have successfully set endnote options in a Word document using Aspose.Words for .NET.

### Example source code for Set Endnote Options using Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Feel free to use this code in your own projects and modify it according to your specific requirements.

### FAQ's

#### Q: How can I style endnotes in Aspose.Words?

A: To style endnotes in Aspose.Words, you can use the `EndnoteOptions` class and the `SeparatorNoteTextStyle` property. You can specify font style, size, color, etc. for endnotes using this property.

#### Q: Is it possible to customize the numbering of endnotes in a document?

A: Yes, it is possible to customize the numbering of endnotes in a document. You can use the `RestartRule` and `NumberStyle` properties of the `EndnoteOptions` class to define specific restart rules and numbering styles.

#### Q: How can I position endnotes in a document?

A: To position endnotes in a document, you can use the `Position` property of the `EndnoteOptions` class. You can specify whether endnotes should be placed at the bottom of each page, at the end of each section, or at the end of the document.

#### Q: Can I customize the endnote numbering format?

A: Yes, you can customize the format of endnote numbering in Aspose.Words. Use the `NumberFormat` property of the `EndnoteOptions` class to set the desired format, such as Arabic numerals, Roman numerals, letters, etc.

#### Q: Is it possible to continue endnote numbering between sections of a document?

A: Yes, it is possible to continue endnote numbering between sections of a document. Use the `RestartRule` property of the `EndnoteOptions` class and set it to `RestartContinuous` to allow numbering to continue between sections.
