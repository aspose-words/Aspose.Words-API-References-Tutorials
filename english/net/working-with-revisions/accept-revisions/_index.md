---
title: Accept Revisions
linktitle: Accept Revisions
second_title: Aspose.Words for .NET API Reference
description: Learn how to accept revisions to a Word document using Aspose.Words for .NET
type: docs
weight: 10
url: /net/working-with-revisions/accept-revisions/
---

In this tutorial, we will walk you through accepting revisions to a Word document using the Accept Revisions feature of Aspose.Words for .NET. Follow the steps below to understand the source code and accept changes to the document.

## Step 1: Adding and Editing Document Content

In this example, we are creating a document and adding content. We use several paragraphs to illustrate changes and revisions. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Add text to the first paragraph, then add two more paragraphs.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Step 2: Track reviews and add reviews

We enable revision tracking and add a revision to the document. Here's how:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// This paragraph is a revision and will have the corresponding "IsInsertRevision" flag set.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Step 3: Delete a paragraph and manage revisions

We delete a paragraph and check for saved revisions. Here's how:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// As we are tracking revisions, the paragraph still exists in the document, will have the "IsDeleteRevision" flag set
// and will be displayed as a review in Microsoft Word, until we accept or reject all reviews.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Step 4: Accept Changes

We accept all changes to the document. Here's how:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Step 5: Stop tracking reviews

We're going to stop tracking revisions so that changes to the document no longer show up as revisions. Here's how:

```csharp
doc.StopTrackRevisions();
```
## Step 6: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Example source code for Accept Revisions using Aspose.Words for .NET

Here is the complete source code for accepting changes in a document using Aspose.Words for .NET:


```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Add text to the first paragraph, then add two more paragraphs.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// We have three paragraphs, none of which registered as any type of revision
// If we add/remove any content in the document while tracking revisions,
// they will be displayed as such in the document and can be accepted/rejected.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// This paragraph is a revision and will have the according "IsInsertRevision" flag set.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Get the document's paragraph collection and remove a paragraph.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Since we are tracking revisions, the paragraph still exists in the document, will have the "IsDeleteRevision" set
// and will be displayed as a revision in Microsoft Word, until we accept or reject all revisions.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// The delete revision paragraph is removed once we accept changes.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Stopping the tracking of revisions makes this text appear as normal text.
// Revisions are not counted when the document is changed.
doc.StopTrackRevisions();

// Save the document.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

