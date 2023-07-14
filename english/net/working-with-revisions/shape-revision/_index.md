---
title: Shape Revision
linktitle: Shape Revision
second_title: Aspose.Words Document Processing API
description: Revise shapes in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/shape-revision/
---

In this step-by-step guide, we'll walk you through how to make revisions to shapes in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Creating the document and adding shapes

The first step is to create a new document and add shapes.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Step 2: Track revisions and add another shape

We'll turn on revision tracking and add another shape.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Step 3: Get the shape collection and check for revisions

We'll get the collection of shapes from the document and check the revisions associated with each shape.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Step 4: Checking Shape Move Revisions

We are going to load an existing document containing shape displacement revisions and check the associated revisions.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Example source code for Shape Revision using Aspose.Words for .NET

Here is the complete source code for making revisions to shapes in a document using Aspose.Words for .NET:

```csharp
Document doc = new Document();

// Insert an inline shape without tracking revisions.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Start tracking revisions and then insert another shape.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Get the document's shape collection which includes just the two shapes we added.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Remove the first shape.
shapes[0].Remove();

// Because we removed that shape while changes were being tracked, the shape counts as a delete revision.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// And we inserted another shape while tracking changes, so that shape will count as an insert revision.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// The document has one shape that was moved, but shape move revisions will have two instances of that shape.
// One will be the shape at its arrival destination and the other will be the shape at its original location.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// This is the move to revision, also the shape at its arrival destination.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// This is the move from revision, which is the shape at its original location.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Conclusion

In this tutorial, we learned how to make revisions to shapes in a Word document using Aspose.Words for .NET. By following the steps of creating the document, enabling revision tracking, checking the revisions associated with each shape, and checking the revisions for moving the shapes, we were able to manage the revisions successfully. Aspose.Words for .NET offers a powerful API for Words Processing with reviews and forms in Word documents.

### FAQ's

#### Q: How can I create a new document and add shapes in Aspose.Words for .NET?

A: To create a new document and add shapes in Aspose.Words for .NET, you can use the following code. Here we add two shapes, a cube and a sun, to the first section of the document:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Q: How do I enable revision tracking in Aspose.Words for .NET?

A: To enable revision tracking in Aspose.Words for .NET, you can use the `StartTrackRevisions` method of the `Document` object. This method takes the name of the author of the revisions as a parameter:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Q: How can I check the revisions associated with each shape in an Aspose.Words for .NET document?

A: To check the revisions associated with each shape in an Aspose.Words for .NET document, you can get the document's collection of shapes using the `GetChildNodes` method with the `NodeType.Shape` node type. Then you can access each shape's `IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision`, and `IsMoveToRevision` properties to determine what type of revision is associated with the shape:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Q: How can I check for displacement revisions of shapes in an Aspose.Words for .NET document?

A: To check for shape displacement revisions in an Aspose.Words for .NET document, you can load an existing document that contains shape displacement revisions. Then you can access each shape's `IsMoveFromRevision` and `IsMoveToRevision` properties to determine if it is being moved and if so, from where and to where:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```
