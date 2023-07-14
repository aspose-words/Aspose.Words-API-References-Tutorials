---
title: Horizontale Zusammenführung
linktitle: Horizontale Zusammenführung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Zellen in einer Word-Tabelle horizontal zusammenführen.
type: docs
weight: 10
url: /de/net/programming-with-tables/horizontal-merge/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument horizontal zusammenführen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Zellen in Ihren Word-Tabellen programmgesteuert horizontal zusammenzuführen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentengenerators
Um die Textverarbeitung mit der Tabelle und den Zellen zu starten, müssen wir ein neues Dokument erstellen und den Dokumentgenerator initialisieren. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und initialisieren Sie den Dokumentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Aufbau der Tabelle mit horizontaler Zellenverschmelzung
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

 Hier verwenden wir den Document Builder, um die Tabelle zu erstellen und die Eigenschaften für die horizontale Zusammenführung der Zellen festzulegen. Wir benutzen das`HorizontalMerge`Eigentum der`CellFormat` -Objekt, um den Typ der horizontalen Zusammenführung anzugeben, der auf jede Zelle angewendet werden soll. Benutzen`CellMerge.First` Wir verschmelzen die erste Zelle mit der nächsten, während wir sie verwenden`CellMerge.Previous` Wir verschmelzen die aktuelle Zelle mit der vorherigen Zelle.`CellMerge.None` gibt an, dass die Zelle nicht zusammengeführt werden soll.

## Schritt 4: Speichern des geänderten Dokuments
Schließlich müssen wir das geänderte Dokument mit horizontal zusammengeführten Zellen speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für Horizontal Merge mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Zellen in einer Tabelle in einem Word-Dokument horizontal zusammenführt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die horizontale Zellenzusammenführung in Ihren Word-Tabellen programmgesteuert anwenden. Mit dieser Funktion können Sie komplexere Tabellenlayouts erstellen und Ihre Daten besser organisieren.