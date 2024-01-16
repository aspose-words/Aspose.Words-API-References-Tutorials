---
title: Formatierte Tabelle
linktitle: Formatierte Tabelle
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine formatierte Tabelle in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-tables/formatted-table/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine formatierte Tabelle in einem Word-Dokument erstellen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, programmgesteuert Tabellen mit benutzerdefinierter Formatierung in Ihren Word-Dokumenten zu erstellen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentengenerators
Um mit dem Aufbau der formatierten Tabelle zu beginnen, müssen wir ein neues Dokument erstellen und den Dokumentgenerator initialisieren. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und initialisieren Sie den Dokumentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Erstellen der formatierten Tabelle
Als Nächstes erstellen wir die formatierte Tabelle mit den vom Document Builder bereitgestellten Methoden. Verwenden Sie den folgenden Code:

```csharp
// Beginnen Sie mit dem Aufbau des Arrays
Table table = builder. StartTable();

// Aufbau der Tabellenkopfzeile
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Aufbau des Array-Körpers
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Ende des Array-Aufbaus
builder. EndTable();
```

 Hier verwenden wir den Document Builder, um die Tabelle Schritt für Schritt aufzubauen. Wir beginnen mit einem Anruf`StartTable()` um die Tabelle zu initialisieren. Dann verwenden wir`InsertCell()` Zellen einfügen und`Write()` um Inhalt zu jeder Zelle hinzuzufügen. Wir verwenden auch verschiedene Formatierungseigenschaften, um die Formatierung von Tabellenzeilen, Zellen und Text zu definieren.

## Schritt 4: Speichern Sie das Dokument
Schließlich müssen wir das Dokument mit der formatierten Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das Dokument
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für eine formatierte Tabelle mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Die tabellenweite Formatierung muss angewendet werden, nachdem mindestens eine Zeile in der Tabelle vorhanden ist.
	table.LeftIndent = 20.0;
	// Legen Sie die Höhe fest und definieren Sie die Höhenregel für die Kopfzeile.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Wir müssen die Breite dieser Zelle nicht angeben, da sie von der vorherigen Zelle geerbt wird.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Setzen Sie die Höhe zurück und definieren Sie eine andere Höhenregel für den Tabellenkörper.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Setzen Sie die Schriftartformatierung zurück.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine formatierte Tabelle in einem Word-Dokument erstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie benutzerdefinierte Tabellen mit spezifischer Formatierung in Ihren Word-Dokumenten programmgesteuert erstellen. Mit dieser Funktion können Sie Ihre Daten optisch ansprechend und organisiert präsentieren und strukturieren.