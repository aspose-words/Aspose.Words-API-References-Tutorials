---
title: Zum Zusammenführungsfeld verschieben
linktitle: Zum Zusammenführungsfeld verschieben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie anhand der Schritt-für-Schritt-Anleitung, wie Sie die Funktion „In Merge-Feld verschieben“ in Aspose.Words für .NET implementieren.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-merge-field/
---

In diesem Beispiel untersuchen wir die Funktion „In Merge-Feld verschieben“ von Aspose.Words für .NET. Aspose.Words ist eine leistungsstarke Dokumentbearbeitungsbibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert zu erstellen, zu ändern und zu konvertieren. Mit der Funktion „In Zusammenführungsfeld verschieben“ können wir zu Zusammenführungsfeldern innerhalb eines Dokuments navigieren und verschiedene Vorgänge daran ausführen.


## Den Quellcode Schritt für Schritt erklären

Lassen Sie uns den Quellcode Schritt für Schritt durchgehen, um zu verstehen, wie Sie die Funktion „In Zusammenführungsfeld verschieben“ mit Aspose.Words für .NET verwenden.

## Schritt 1: Initialisieren des Dokuments und des Dokument-Builders

Initialisieren Sie zunächst die Objekte Document und DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Einfügen eines Zusammenführungsfelds und Hinzufügen von Text dahinter

Verwenden Sie die InsertField-Methode der DocumentBuilder-Klasse, um ein Briefvorlagenfeld einzufügen und anschließend Text hinzuzufügen:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Schritt 3: Der Cursor des Builders befindet sich derzeit am Ende des Dokuments.

```csharp
Assert.Null(builder.CurrentNode);
```
## Schritt 4: Bewegen Sie den Document Builder-Cursor zum Zusammenführungsfeld

Um den Document Builder-Cursor zum Briefvorlagenfeld zu bewegen, verwenden Sie die MoveToField-Methode der DocumentBuilder-Klasse:

```csharp
builder.MoveToField(field, true);
```

## Text direkt nach dem Zusammenführungsfeld hinzufügen

Sobald sich der Document Builder-Cursor im Zusammenführungsfeld befindet, können Sie mit der Write-Methode direkt danach Text hinzufügen:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Beispielquellcode für „In Merge-Feld verschieben“ mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie mit dem DocumentBuilder ein Feld ein und fügen Sie danach eine Textzeile hinzu.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Der Cursor des Builders befindet sich derzeit am Ende des Dokuments.
Assert.Null(builder.CurrentNode);
// Wir können den Builder auf ein Feld wie dieses verschieben, indem wir den Cursor direkt hinter dem Feld platzieren.
builder.MoveToField(field, true);

// Beachten Sie, dass sich der Cursor an einer Stelle hinter dem FieldEnd-Knoten des Feldes befindet, was bedeutet, dass wir uns nicht tatsächlich innerhalb des Feldes befinden.
// Wenn wir den DocumentBuilder in ein Feld verschieben möchten,
// Wir müssen es mit der Methode DocumentBuilder.MoveTo() in den FieldStart- oder FieldSeparator-Knoten eines Feldes verschieben.
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Abschluss

Wir haben die Funktion „In Zusammenführungsfeld verschieben“ von Aspose.Words für .NET untersucht. Wir haben gelernt, wie man mithilfe der DocumentBuilder-Klasse zu Zusammenführungsfeldern innerhalb eines Dokuments navigiert und Operationen daran durchführt. Diese Funktion ist bei der programmgesteuerten Textverarbeitung mit Zusammenführung nützlich

