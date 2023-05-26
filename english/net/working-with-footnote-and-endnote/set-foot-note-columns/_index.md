---
title: Set Foot Note Columns
linktitle: Set Foot Note Columns
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the number of columns for footnotes in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-footnote-and-endnote/set-foot-note-columns/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to set the number of columns for footnotes in a Word document. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the Document Object

First, initialize the `Document` object by providing the path to your source document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Step 2: Setting Footnote Columns

Next, access the `FootnoteOptions` property of the document and set the `Columns` property to specify the number of columns for footnotes. In this example, we set it to 3 columns:

```csharp
doc.FootnoteOptions.Columns = 3;
```

## Step 3: Saving the Document

Finally, save the modified document:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

That's it! You have successfully set the number of columns for footnotes in a Word document using Aspose.Words for .NET.

### Example source code for Set Footnote Columns using Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// Specify the number of columns with which the footnotes area is formatted.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Feel free to use this code in your own projects and modify it according to your specific requirements.