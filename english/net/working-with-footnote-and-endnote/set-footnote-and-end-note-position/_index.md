---
title: Set Footnote And End Note Position
linktitle: Set Footnote And End Note Position
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the position of footnotes and endnotes in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to set the position of footnotes and endnotes in a Word document. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by providing the path to your source document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Step 2: Setting Footnote and Endnote Position

Next, access the `FootnoteOptions` and `EndnoteOptions` properties of the document to set the position of footnotes and endnotes. In this example, we set the position of footnotes to be beneath the text and the position of endnotes to be at the end of the section:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Step 3: Saving the Document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

That's it! You have successfully set the position of footnotes and endnotes in a Word document using Aspose.Words for .NET.

### Example source code for Set Footnote And Endnote Position using Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Feel free to use this code in your own projects and modify it according to your specific requirements.

