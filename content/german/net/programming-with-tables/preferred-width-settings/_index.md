---
title: Bevorzugte Breiteneinstellungen
linktitle: Bevorzugte Breiteneinstellungen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET bevorzugte Tabellenzellenbreiten in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-tables/preferred-width-settings/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET bevorzugte Breiteneinstellungen für Tabellenzellen in einem Word-Dokument festlegt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie verschiedene bevorzugte Breiten für Ihre Tabellenzellen in Ihren Word-Dokumenten festlegen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentgenerators
Um die Textverarbeitung mit dem Dokument- und Dokumentgenerator zu starten, führen Sie diese Schritte aus:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumenterstellung
Document doc = new Document();

// Initialisieren des Dokumentgenerators
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Erstellen der Tabelle mit bevorzugten Breiten
Als Nächstes erstellen wir eine Tabelle mit drei Zellen, die unterschiedliche bevorzugte Breiten haben. Verwenden Sie den folgenden Code:

```csharp
// Beginn der Tabelle
builder. StartTable();

// Einfügen einer Zelle absoluter Größe
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Einfügen einer Zelle mit relativer Größe (in Prozent)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Einfügen einer Zelle mit automatischer Größenanpassung
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Ende der Tabelle
builder. EndTable();
```

Hier verwenden wir den Dokumentgenerator, um eine Tabelle mit drei Zellen zu erstellen. Die erste Zelle hat eine bevorzugte Breite von 40 Punkten, die zweite Zelle hat eine bevorzugte Breite von 20 % der Tabellenbreite und die dritte Zelle hat eine automatische bevorzugte Breite, die sich anpasst

  abhängig vom verfügbaren Platz.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit den bevorzugten Breiteneinstellungen für die Tabellenzellen speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode für bevorzugte Breiteneinstellungen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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
	// Fügen Sie eine Zelle mit relativer (prozentueller) Größe ein.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Fügen Sie eine Zelle mit automatischer Größenanpassung ein.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.Words für .NET bevorzugte Breiteneinstellungen für Tabellenzellen in einem Word-Dokument festlegen. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die Breite Ihrer Tabellenzellen in Ihren Word-Dokumenten an Ihre spezifischen Anforderungen anpassen.