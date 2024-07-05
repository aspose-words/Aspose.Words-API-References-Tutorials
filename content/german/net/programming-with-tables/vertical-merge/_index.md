---
title: Vertikale Zusammenführung
linktitle: Vertikale Zusammenführung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument vertikal zusammenführen.
type: docs
weight: 10
url: /de/net/programming-with-tables/vertical-merge/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument vertikal zusammenführt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Zellen in Ihren Tabellen in Word-Dokumenten vertikal zusammenführen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Dokument einlegen
Um die Textverarbeitung mit dem Dokument zu starten, führen Sie diese Schritte aus:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Neues Dokument erstellen
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Zellen vertikal zusammenführen
Als nächstes werden wir die Zellen in der Tabelle vertikal zusammenführen. Verwenden Sie den folgenden Code:

```csharp
// Einfügen einer Zelle
builder. InsertCell();

// Vertikale Zusammenführung auf die erste Zelle anwenden
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Einfügen einer weiteren Zelle
builder. InsertCell();

// Keine vertikale Zusammenführung auf die Zelle anwenden
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Einfügen einer Zelle
builder. InsertCell();

// Vertikale Zusammenführung mit der vorherigen Zelle anwenden
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Einfügen einer weiteren Zelle
builder. InsertCell();

// Keine vertikale Zusammenführung auf die Zelle anwenden
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Beenden Sie die Erstellung der Tabelle
builder. EndTable();
```

In diesem Code verwenden wir den DocumentBuilder-Konstruktor, um Zellen in eine Tabelle einzufügen. Wir wenden mithilfe der Eigenschaft CellFormat.VerticalMerge eine vertikale Zusammenführung auf Zellen an. Wir verwenden CellMerge.First für die Zusammenführung der ersten Zelle, CellMerge.Previous für die Zusammenführung mit der vorherigen Zelle und CellMerge.None für keine vertikale Zusammenführung.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit den zusammengeführten Zellen speichern. Verwenden Sie dazu den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispiel-Quellcode für Vertical Merge mit Aspose.Words für .NET 
```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Diese Zelle ist vertikal mit der Zelle darüber verbunden und sollte leer sein.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument vertikal zusammenführt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Zellen in Ihren Tabellen problemlos vertikal zusammenführen.