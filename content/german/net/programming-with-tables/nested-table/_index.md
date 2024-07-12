---
title: Verschachtelte Tabelle
linktitle: Verschachtelte Tabelle
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine verschachtelte Tabelle in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-tables/nested-table/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine verschachtelte Tabelle in einem Word-Dokument erstellt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie verschachtelte Tabellen programmgesteuert in Ihren Word-Dokumenten erstellen.

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

## Schritt 3: Erstellen der verschachtelten Tabelle
Als Nächstes erstellen wir die verschachtelte Tabelle, indem wir Zellen in die äußere Tabelle einfügen und innerhalb der ersten Zelle eine neue Tabelle erstellen. Verwenden Sie den folgenden Code:

```csharp
// Einfügen der ersten Zelle der äußeren Tabelle
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Einfügen der zweiten Zelle der äußeren Tabelle
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Beendigung der äußeren Tabelle
builder. EndTable();

// Zur ersten Zelle der äußeren Tabelle wechseln
builder.MoveTo(cell.FirstParagraph);

// Bauen Sie den inneren Tisch
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Ende der inneren Tabelle
builder. EndTable();
```

Hier verwenden wir den Dokumentgenerator, um Zellen und Inhalt in die äußere Tabelle einzufügen. Dann bewegen wir den Cursor des Dokumentgenerators zur ersten Zelle der äußeren Tabelle und erstellen darin eine neue Tabelle, indem wir Zellen und Inhalt einfügen.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit der verschachtelten Tabelle speichern. Verwenden Sie dazu den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode für verschachtelte Tabellen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Dieser Aufruf ist wichtig, um innerhalb der ersten Tabelle eine geschachtelte Tabelle zu erstellen.
	//Ohne diesen Aufruf werden die unten eingefügten Zellen an die äußere Tabelle angehängt.
	builder.EndTable();
	// Zur ersten Zelle der äußeren Tabelle wechseln.
	builder.MoveTo(cell.FirstParagraph);
	// Bauen Sie den inneren Tisch.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine verschachtelte Tabelle in einem Word-Dokument erstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie verschachtelte Tabellen entsprechend Ihren spezifischen Anforderungen programmgesteuert in Ihren Word-Dokumenten erstellen.
