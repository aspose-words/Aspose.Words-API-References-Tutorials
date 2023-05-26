---
title: Vertikale Zusammenführung
linktitle: Vertikale Zusammenführung
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument vertikal zusammenführen.
type: docs
weight: 10
url: /de/net/programming-with-tables/vertical-merge/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument vertikal zusammenführen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Zellen in Ihren Tabellen in Word-Dokumenten vertikal zusammenzuführen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments
Führen Sie die folgenden Schritte aus, um mit der Arbeit mit dem Dokument zu beginnen:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie ein neues Dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Zellen vertikal zusammenführen
Als nächstes werden wir die Zellen vertikal in der Tabelle zusammenführen. Verwenden Sie den folgenden Code:

```csharp
// Fügen Sie eine Zelle ein
builder. InsertCell();

// Wenden Sie die vertikale Zusammenführung auf die erste Zelle an
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Fügen Sie eine weitere Zelle ein
builder. InsertCell();

// Wenden Sie keine vertikale Zusammenführung auf die Zelle an
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Fügen Sie eine Zelle ein
builder. InsertCell();

// Wenden Sie die vertikale Zusammenführung mit der vorherigen Zelle an
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Fügen Sie eine weitere Zelle ein
builder. InsertCell();

// Wenden Sie keine vertikale Zusammenführung auf die Zelle an
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Beenden Sie die Erstellung der Tabelle
builder. EndTable();
```

In diesem Code verwenden wir den DocumentBuilder-Konstruktor, um Zellen in eine Tabelle einzufügen. Mithilfe der CellFormat.VerticalMerge-Eigenschaft wenden wir die vertikale Zusammenführung auf Zellen an. Wir verwenden CellMerge.First für die erste Zellzusammenführung, CellMerge.Previous für die Zusammenführung mit der vorherigen Zelle und CellMerge.None für keine vertikale Zusammenführung.

## Schritt 4: Speichern des geänderten Dokuments
Schließlich müssen wir das geänderte Dokument mit den zusammengeführten Zellen speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für Vertical Merge mit Aspose.Words für .NET 
```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument vertikal zusammenführt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie vertikale Zellen in Ihren Tabellen problemlos zusammenführen.