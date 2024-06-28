---
title: Bevorzugte Breiteneinstellungen
linktitle: Bevorzugte Breiteneinstellungen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET bevorzugte Tabellenzellenbreiten in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-tables/preferred-width-settings/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET bevorzugte Breiteneinstellungen für Tabellenzellen in einem Word-Dokument festlegen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, unterschiedliche bevorzugte Breiten für Ihre Tabellenzellen in Ihren Word-Dokumenten festzulegen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentengenerators
Um die Textverarbeitung mit dem Dokument und dem Dokumentengenerator zu starten, gehen Sie folgendermaßen vor:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung
Document doc = new Document();

// Initialisieren Sie den Dokumentgenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Erstellen Sie den Tisch mit den gewünschten Breiten
Als Nächstes erstellen wir eine Tabelle mit drei Zellen mit unterschiedlichen bevorzugten Breiten. Verwenden Sie den folgenden Code:

```csharp
// Anfang der Tabelle
builder. StartTable();

// Fügen Sie eine Zelle mit absoluter Größe ein
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Fügen Sie eine Zelle mit relativer Größe (in Prozent) ein.
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Fügen Sie eine Zelle mit automatischer Größe ein
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Ende des Tisches
builder. EndTable();
```

Hier verwenden wir den Document Builder, um eine Tabelle mit drei Zellen zu erstellen. Die erste Zelle hat eine bevorzugte Breite von 40 Punkten, die zweite Zelle hat eine bevorzugte Breite von 20 % der Tabellenbreite und die dritte Zelle hat eine automatische bevorzugte Breite, die sich anpasst.

  je nach verfügbarem Platz.

## Schritt 4: Speichern des geänderten Dokuments
Abschließend müssen wir das geänderte Dokument mit den bevorzugten Breiteneinstellungen speichern, die für die Tabellenzellen definiert sind. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für bevorzugte Breiteneinstellungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Fügen Sie eine Tabellenzeile ein, die aus drei Zellen besteht, die unterschiedliche bevorzugte Breiten haben.
	builder.StartTable();
	// Fügen Sie eine Zelle mit absoluter Größe ein.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Fügen Sie eine Zelle mit relativer Größe (Prozent) ein.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Fügen Sie eine Zelle mit automatischer Größe ein.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET bevorzugte Breiteneinstellungen für Tabellenzellen in einem Word-Dokument festlegt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die Breite Ihrer Tabellenzellen in Ihren Word-Dokumenten an Ihre spezifischen Anforderungen anpassen.