---
title: Show Revisions In Balloons
linktitle: Show Revisions In Balloons
second_title: Aspose.Words for .NET API Reference
description: Show revisions in balloons with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/show-revisions-in-balloons/
---

In this step-by-step guide, we are going to show you how to show revisions in balloons in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Configure review show options

We will configure the show options to make revisions visible in balloons.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Step 3: Save the document in PDF format

Finally, we'll save the document as a PDF with the revisions Showed in balloons.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown output formats

The output can be formatted in markdown to improve readability. For example :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Example source code for Show Revisions In Balloons using Aspose.Words for .NET

Here is the complete source code to show revisions in balloons in a document using Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Renders insert revisions inline, delete and format revisions in balloons.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Renders revision bars on the right side of a page.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Conclusion

In this tutorial, we learned how to display revisions in balloons in a Word document using Aspose.Words for .NET. By using the appropriate display options, we were able to make the revisions visible in bubbles with revision bars on the right side. Aspose.Words for .NET offers many powerful features for manipulating Word documents, including revision management. Now you can use this knowledge to show revisions in balloons in your own Word documents using Aspose.Words for .NET.


### FAQ's

#### Q: How to upload a document in Aspose.Words for .NET?

A: Use the `Document` class of Aspose.Words for .NET to load a document from a file. You can specify the full document path.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: How to display revisions in balloons with Aspose.Words for .NET?

A: Use the `ShowInBalloons` property of the `RevisionOptions` object to configure the display of revisions in balloons. You can set this property on `ShowInBalloons.FormatAndDelete` to show revisions in balloons with deletion and formatting revisions.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Q: How to save a document in PDF format with Aspose.Words for .NET?

A: Use the `Save` method of the `Document` object to save the document in PDF format. You must specify the full destination path with the ".pdf" extension.

```csharp
doc.Save("path/to/destination/document.pdf");
```
