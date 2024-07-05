---
title: Formrevision
linktitle: Formrevision
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Überarbeiten Sie Formen in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/shape-revision/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Änderungen an Formen in einem Word-Dokument vornehmen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Erstellen des Dokuments und Hinzufügen von Formen

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

## Schritt 2: Revisionen verfolgen und eine weitere Form hinzufügen

Wir aktivieren die Revisionsverfolgung und fügen eine weitere Form hinzu.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Schritt 3: Holen Sie sich die Shape-Sammlung und prüfen Sie, ob es Änderungen gibt

Wir holen die Sammlung der Formen aus dem Dokument und überprüfen die mit jeder Form verknüpften Revisionen.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Schritt 4: Überprüfen der Formverschiebungsrevisionen

Wir laden ein vorhandenes Dokument, das Revisionen der Formverschiebung enthält, und überprüfen die zugehörigen Revisionen.

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

Hier ist der vollständige Quellcode zum Bearbeiten von Formen in einem Dokument mit Aspose.Words für .NET:

```csharp
Document doc = new Document();

//Fügen Sie eine Inline-Form ein, ohne Revisionen zu verfolgen.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Beginnen Sie mit der Revisionsverfolgung und fügen Sie dann eine weitere Form ein.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Holen Sie sich die Formsammlung des Dokuments, die nur die beiden von uns hinzugefügten Formen enthält.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Entfernen Sie die erste Form.
shapes[0].Remove();

// Da wir diese Form entfernt haben, während die Änderungen nachverfolgt wurden, zählt die Form als gelöschte Revision.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Und wir haben beim Nachverfolgen der Änderungen eine weitere Form eingefügt, sodass diese Form als eingefügte Revision zählt.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Das Dokument enthält eine Form, die verschoben wurde, bei Revisionen durch Formverschiebung gibt es jedoch zwei Instanzen dieser Form.
// Eine davon ist die Form am Zielort und die andere die Form an ihrem ursprünglichen Standort.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Dies ist der Übergang zur Überarbeitung und zugleich die Form an ihrem Zielort.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Dies ist die Verschiebung von der Revision, bei der sich die Form an ihrer ursprünglichen Position befindet.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Überarbeitungen an Formen in einem Word-Dokument vornimmt. Indem wir die Schritte zum Erstellen des Dokuments, Aktivieren der Überarbeitungsverfolgung, Überprüfen der mit jeder Form verknüpften Überarbeitungen und Überprüfen der Überarbeitungen zum Verschieben der Formen befolgten, konnten wir die Überarbeitungen erfolgreich verwalten. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Überprüfungen und Formularen in Word-Dokumenten.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words für .NET ein neues Dokument erstellen und Formen hinzufügen?

A: Um ein neues Dokument zu erstellen und Formen in Aspose.Words für .NET hinzuzufügen, können Sie den folgenden Code verwenden. Hier fügen wir dem ersten Abschnitt des Dokuments zwei Formen hinzu, einen Würfel und eine Sonne:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### F: Wie aktiviere ich die Revisionsverfolgung in Aspose.Words für .NET?

 A: Um die Revisionsverfolgung in Aspose.Words für .NET zu aktivieren, können Sie den`StartTrackRevisions` Methode der`Document` Objekt. Diese Methode verwendet den Namen des Autors der Revisionen als Parameter:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### F: Wie kann ich die Revisionen überprüfen, die mit jeder Form in einem Aspose.Words-Dokument für .NET verknüpft sind?

A: Um die Revisionen zu überprüfen, die mit jeder Form in einem Aspose.Words für .NET-Dokument verknüpft sind, können Sie die Sammlung der Formen des Dokuments mithilfe des`GetChildNodes` Methode mit dem`NodeType.Shape` Knotentyp. Dann können Sie auf die einzelnen Formen zugreifen`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , Und`IsMoveToRevision` Eigenschaften, um zu bestimmen, welcher Revisionstyp mit der Form verknüpft ist:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### F: Wie kann ich in einem Aspose.Words-Dokument für .NET nach Verschiebungsrevisionen von Formen suchen?

 A: Um in einem Aspose.Words für .NET-Dokument nach Formverschiebungsrevisionen zu suchen, können Sie ein vorhandenes Dokument laden, das Formverschiebungsrevisionen enthält. Dann können Sie auf die Formverschiebungsrevisionen der einzelnen Formen zugreifen.`IsMoveFromRevision` Und`IsMoveToRevision` Eigenschaften, um zu bestimmen, ob es verschoben wird und wenn ja, von wo und wohin:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```