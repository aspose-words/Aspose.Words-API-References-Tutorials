---
title: Tabelle direkt einfügen
linktitle: Tabelle direkt einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle direkt in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-tables/insert-table-directly/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle direkt in ein Word-Dokument einfügen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Tabellen programmgesteuert direkt in Ihre Word-Dokumente einzufügen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Dokument und Tabelle erstellen
Um die Textverarbeitung mit dem Array zu starten, müssen wir ein neues Dokument erstellen und das Array initialisieren. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung
Document doc = new Document();

//Erstellen Sie das Array
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Aufbau des Arrays
Als Nächstes erstellen wir die Tabelle, indem wir Zeilen und Zellen hinzufügen. Verwenden Sie den folgenden Code als Beispiel:

```csharp
// Erstellen Sie die erste Zeile
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Erstellen Sie die erste Zelle
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplizieren Sie die Zelle für die zweite Zelle in der Zeile
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Hier erstellen wir eine Zeile mit dem`AllowBreakAcrossPages` Eigenschaft festgelegt auf`true` um Seitenumbrüche zwischen Zeilen zu ermöglichen. Anschließend erstellen wir eine Zelle mit farbigem Hintergrund, fester Breite und angegebenem Textinhalt. Anschließend duplizieren wir diese Zelle, um die zweite Zelle in der Zeile zu erstellen.

## Schritt 4: Tabelle automatisch anpassen
Wir können automatische Anpassungen an der Tabelle vornehmen, um sie korrekt zu formatieren. Verwenden Sie den folgenden Code:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Diese Codezeile wendet eine automatische Anpassung basierend auf festen Spaltenbreiten an.

## Schritt 5: Registrieren des

  geändertes Dokument
Abschließend müssen wir das geänderte Dokument mit der direkt eingefügten Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für „Tabelle direkt einfügen“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Wir beginnen mit der Erstellung des Tabellenobjekts. Beachten Sie, dass wir das Dokumentobjekt übergeben müssen
	//an den Konstruktor jedes Knotens. Dies liegt daran, dass jeder Knoten, den wir erstellen, dazugehören muss
	// zu einem Dokument.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Hier könnten wir ConsiderMinimum aufrufen, um die Zeilen und Zellen für uns zu erstellen. Diese Methode wird verwendet
	// um sicherzustellen, dass der angegebene Knoten gültig ist. In diesem Fall sollte eine gültige Tabelle mindestens eine Zeile und eine Zelle haben.
	// Stattdessen übernehmen wir die Erstellung der Zeile und Tabelle selbst.
	// Dies wäre der beste Weg, dies zu tun, wenn wir eine Tabelle innerhalb eines Algorithmus erstellen würden.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Wir können jetzt alle Einstellungen für die automatische Anpassung anwenden.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Anschließend wiederholen wir den Vorgang für die anderen Zellen und Zeilen in der Tabelle.
	// Wir können die Arbeit auch beschleunigen, indem wir vorhandene Zellen und Zeilen klonen.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle direkt in ein Word-Dokument einfügt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen direkt programmgesteuert in Ihre Word-Dokumente einfügen. Mit dieser Funktion können Sie Tabellen erstellen und entsprechend Ihren spezifischen Anforderungen anpassen.