---
title: Move Node In Tracked Document
linktitle: Move Node In Tracked Document
second_title: Aspose.Words for .NET API Reference
description: Move nodes in a tracked document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/move-node-in-tracked-document/
---

In this step-by-step guide, we'll walk you through how to move a node in a tracked Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Creating the document

The first step is to create a new document and add paragraphs.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Step 2: Track revisions

We are going to enable revision tracking in the document.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Step 3: Move a node

We will move a node (paragraph) from one position to another while generating revisions.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Step 4: Stop Tracking Reviews

We will stop tracking revisions in the document.

```csharp
doc.StopTrackRevisions();
```

## Step 5: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Example source code for Move Node In Tracked Document using Aspose.Words for .NET

Here is the full source code for moving a node in a tracked document using Aspose.Words for .NET:


```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Start tracking revisions.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Generate revisions when moving a node from one location to another.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Stop the process of tracking revisions.
doc.StopTrackRevisions();

// There are 3 additional paragraphs in the move-from range.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


