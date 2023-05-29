---
title: Remove Comments In Pdf
linktitle: Remove Comments In Pdf
second_title: Aspose.Words for .NET API Reference
description: Remove comments in a PDF file with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/remove-comments-in-pdf/
---

In this step-by-step guide, we are going to tell you how to remove comments in a PDF file using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to load the document containing the comments.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Hide comments in PDF

We will configure the layout option to hide comments when generating the PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Step 3: Save the document as a PDF

Finally, we will save the document in PDF format by deleting the comments.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown output formats

The output can be formatted in markdown to improve readability. For example :

```markdown
- Comments are hidden in the generated PDF.
```

### Example source code for Remove Comments In Pdf using Aspose.Words for .NET

Here is the complete source code to remove comments in a PDF file using Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Hide comments in the PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```
