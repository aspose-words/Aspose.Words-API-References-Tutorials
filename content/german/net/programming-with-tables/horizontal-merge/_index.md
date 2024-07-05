---
title: Horizontale Zusammenführung
linktitle: Horizontale Zusammenführung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Zellen in einer Word-Tabelle horizontal zusammenführen.
type: docs
weight: 10
url: /de/net/programming-with-tables/horizontal-merge/
---

In diesem Tutorial lernen wir, wie man Zellen in einer Tabelle in einem Word-Dokument mit Aspose.Words für .NET horizontal zusammenführt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Zellen in Ihren Word-Tabellen programmgesteuert horizontal zusammenführen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentgenerators
Um Words Processing mit der Tabelle und den Zellen zu starten, müssen wir ein neues Dokument erstellen und den Dokumentgenerator initialisieren. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und initialisieren Sie den Dokumentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Erstellen der Tabelle mit horizontaler Zellverbindung
Als Nächstes erstellen wir die Tabelle und wenden die horizontale Zellenzusammenführung mithilfe der von Aspose.Words für .NET bereitgestellten Eigenschaften an. Verwenden Sie den folgenden Code:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Diese Zelle wird mit der vorherigen zusammengeführt und sollte leer sein.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Hier verwenden wir den Dokumentgenerator, um die Tabelle zu erstellen und die Eigenschaften für die horizontale Zellzusammenführung festzulegen. Wir verwenden den`HorizontalMerge` Eigentum der`CellFormat` Objekt, um den Typ der horizontalen Zusammenführung anzugeben, der auf jede Zelle angewendet werden soll.`CellMerge.First` Wir verschmelzen die erste Zelle mit der nächsten, indem wir`CellMerge.Previous` wir führen die aktuelle Zelle mit der vorherigen Zelle zusammen.`CellMerge.None` gibt an, dass die Zelle nicht zusammengeführt werden soll.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit horizontal zusammengeführten Zellen speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode für Horizontal Merge mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Diese Zelle wird mit der vorherigen zusammengeführt und sollte leer sein.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument horizontal zusammenführt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die horizontale Zellenzusammenführung programmgesteuert in Ihren Word-Tabellen anwenden. Mit dieser Funktion können Sie komplexere Tabellenlayouts erstellen und Ihre Daten besser organisieren.