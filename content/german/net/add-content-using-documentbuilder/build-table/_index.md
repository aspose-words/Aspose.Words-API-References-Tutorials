---
title: Erstellen Sie eine Tabelle in einem Word-Dokument
linktitle: Erstellen Sie eine Tabelle in einem Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/build-table/
---
In diesem Schritt-für-Schritt-Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument erstellen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Handbuchs werden Sie in der Lage sein, mithilfe der DocumentBuilder-Klasse eine Tabelle mit benutzerdefinierter Formatierung und Inhalt zu erstellen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Starten Sie die Tabelle
Als nächstes verwenden Sie die StartTable-Methode der DocumentBuilder-Klasse, um mit dem Aufbau der Tabelle zu beginnen:

```csharp
Table table = builder.StartTable();
```

## Schritt 3: Zellen einfügen und Inhalt hinzufügen
Jetzt können Sie Zellen in die Tabelle einfügen und ihnen Inhalte hinzufügen, indem Sie die Methoden InsertCell und Write der DocumentBuilder-Klasse verwenden. Passen Sie die Zellenformatierung nach Bedarf an:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Schritt 4: Beenden Sie die Reihe
Nachdem Sie den Zellen der ersten Zeile Inhalt hinzugefügt haben, verwenden Sie die EndRow-Methode der DocumentBuilder-Klasse, um die Zeile zu beenden:

```csharp
builder.EndRow();
```

## Schritt 5: Passen Sie die Zeilenformatierung an
Sie können die Formatierung einer Zeile anpassen, indem Sie Eigenschaften der RowFormat- und CellFormat-Objekte festlegen:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Schritt 6: Beenden Sie den Tisch
Um die Tabelle zu vervollständigen, verwenden Sie die EndTable-Methode der DocumentBuilder-Klasse:

```csharp
builder.EndTable();
```

### Beispielquellcode zum Erstellen einer Tabelle mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Erstellen einer Tabelle mit Aspose.Words für .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument erstellen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt Tabellen mit benutzerdefinierter Formatierung erstellen.

### FAQs zur Erstellungstabelle in einem Word-Dokument

#### F: Was ist Aspose.Words für .NET?

A: Aspose.Words für .NET ist eine leistungsstarke Dokumentverarbeitungsbibliothek, die es Entwicklern ermöglicht, Microsoft Word-Dokumente programmgesteuert in .NET-Anwendungen zu erstellen, zu lesen, zu bearbeiten und zu konvertieren. Es bietet eine breite Palette von Funktionen für die Arbeit mit Word-Dokumenten, wie z. B. Textbearbeitung, Tabellenerstellung, Dokumentschutz, Formatierung und mehr.

#### F: Wie kann ich mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument erstellen?

A: Um mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument zu erstellen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine neue Instanz von`Document` Klasse und a`DocumentBuilder` Objekt.
2.  Benutzen Sie die`StartTable` Methode der`DocumentBuilder`Klasse, um mit dem Aufbau der Tabelle zu beginnen.
3.  Fügen Sie Zellen in die Tabelle ein und fügen Sie Inhalte hinzu, indem Sie verwenden`InsertCell` Und`Write` Methoden der`DocumentBuilder` Klasse.
4.  Beenden Sie die Reihe mit`EndRow` Methode der`DocumentBuilder` Klasse.
5.  Passen Sie die Zeilenformatierung an, indem Sie die Eigenschaften festlegen`RowFormat` Und`CellFormat` Objekte.
6.  Beenden Sie die Tabelle mit`EndTable` Methode der`DocumentBuilder` Klasse.
7. Speichern Sie das Dokument.

#### F: Wie kann ich die Formatierung der Tabelle und ihrer Zellen anpassen?

 A: Sie können die Formatierung der Tabelle und ihrer Zellen anpassen, indem Sie verschiedene Eigenschaften festlegen`RowFormat` Und`CellFormat` Objekte. Sie können beispielsweise die Zellenausrichtung, die vertikale und horizontale Textausrichtung, die Zellenhöhe, die Zeilenhöhe und mehr anpassen. Durch die Verwendung dieser Eigenschaften können Sie das gewünschte Erscheinungsbild der Tabelle und ihres Inhalts erzielen.

#### F: Kann ich komplexe Tabellen mit zusammengeführten Zellen und anderen erweiterten Funktionen erstellen?

 A: Ja, Aspose.Words für .NET bietet erweiterte Funktionen zum Erstellen komplexer Tabellen, einschließlich der Unterstützung für verbundene Zellen, verschachtelte Tabellen und komplexe Tabellenlayouts. Du kannst den ... benutzen`MergeCells` Methode zum Zusammenführen von Zellen,`StartTable`Methode zum Erstellen verschachtelter Tabellen und andere Methoden zum Erreichen der gewünschten Tabellenstruktur.

#### F: Ist Aspose.Words für .NET mit verschiedenen Word-Dokumentformaten kompatibel?

A: Ja, Aspose.Words für .NET ist mit verschiedenen Word-Dokumentformaten kompatibel, darunter DOC, DOCX, RTF und mehr. Es unterstützt sowohl ältere Formate (DOC) als auch moderne XML-basierte Formate (DOCX) und ermöglicht Ihnen die problemlose Arbeit mit Dokumenten in verschiedenen Formaten.

#### F: Wo finde ich weitere Informationen und Dokumentation zu Aspose.Words für .NET?

 A: Eine umfassende Dokumentation und Codebeispiele finden Sie unter[API-Referenzen](https://reference.aspose.com/words/net/). Die Dokumentation enthält detaillierte Informationen zu den Funktionen der Bibliothek und deren Verwendung in Ihren .NET-Anwendungen.