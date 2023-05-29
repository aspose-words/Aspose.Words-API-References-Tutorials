---
title: Formrevision
linktitle: Formrevision
second_title: Aspose.Words für .NET API-Referenz
description: Überarbeiten Sie Formen in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/shape-revision/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Änderungen an Formen in einem Word-Dokument vornehmen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokument erstellen und Formen hinzufügen

Der erste Schritt besteht darin, ein neues Dokument zu erstellen und Formen hinzuzufügen.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Schritt 2: Überarbeitungen verfolgen und eine weitere Form hinzufügen

Wir aktivieren die Revisionsverfolgung und fügen eine weitere Form hinzu.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Schritt 3: Holen Sie sich die Formensammlung und prüfen Sie, ob Änderungen vorliegen

Wir rufen die Formensammlung aus dem Dokument ab und überprüfen die mit jeder Form verbundenen Revisionen.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Schritt 4: Überprüfen der Formverschiebungsrevisionen

Wir werden ein vorhandenes Dokument laden, das Formverschiebungsrevisionen enthält, und die zugehörigen Revisionen überprüfen.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Beispielquellcode für Shape Revision mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Überarbeiten von Formen in einem Dokument mit Aspose.Words für .NET:

```csharp
Document doc = new Document();

// Fügen Sie eine Inline-Form ein, ohne Revisionen zu verfolgen.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Beginnen Sie mit der Nachverfolgung von Revisionen und fügen Sie dann eine weitere Form ein.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Rufen Sie die Formensammlung des Dokuments ab, die nur die beiden von uns hinzugefügten Formen enthält.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Entfernen Sie die erste Form.
shapes[0].Remove();

// Da wir diese Form während der Nachverfolgung der Änderungen entfernt haben, gilt die Form als gelöschte Revision.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Und wir haben beim Verfolgen von Änderungen eine weitere Form eingefügt, sodass diese Form als Einfügungsrevision zählt.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//Das Dokument verfügt über eine Form, die verschoben wurde, aber Überarbeitungen der Formverschiebung enthalten zwei Instanzen dieser Form.
// Eine davon ist die Form am Ankunftsziel und die andere die Form an ihrem ursprünglichen Standort.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Dies ist der Schritt zur Überarbeitung, auch die Form an ihrem Zielort.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Dies ist die Verschiebung von der Revision, bei der es sich um die Form an ihrer ursprünglichen Position handelt.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

