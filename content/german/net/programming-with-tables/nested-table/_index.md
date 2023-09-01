---
title: Verschachtelter Tisch
linktitle: Verschachtelter Tisch
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine verschachtelte Tabelle in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-tables/nested-table/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine verschachtelte Tabelle in einem Word-Dokument erstellen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, verschachtelte Tabellen in Ihren Word-Dokumenten programmgesteuert zu erstellen.

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

## Schritt 3: Erstellen der verschachtelten Tabelle
Als Nächstes erstellen wir die verschachtelte Tabelle, indem wir Zellen in die äußere Tabelle einfügen und in der ersten Zelle eine neue Tabelle erstellen. Verwenden Sie den folgenden Code:

```csharp
// Fügen Sie die erste Zelle der äußeren Tabelle ein
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Fügen Sie die zweite Zelle der äußeren Tabelle ein
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Beendigung der äußeren Tabelle
builder. EndTable();

// Gehen Sie zur ersten Zelle der äußeren Tabelle
builder.MoveTo(cell.FirstParagraph);

// Bauen Sie den inneren Tisch
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Ende der inneren Tabelle
builder. EndTable();
```

Hier verwenden wir den Document Builder, um Zellen und Inhalte in die äußere Tabelle einzufügen. Dann bewegen wir den Document Builder-Cursor zur ersten Zelle der äußeren Tabelle und erstellen darin eine neue Tabelle, indem wir Zellen und Inhalte einfügen.

## Schritt 4: Speichern des geänderten Dokuments
Abschließend müssen wir das geänderte Dokument mit der verschachtelten Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und die richtige Namensdatei für das Ausgabedokument angeben.

### Beispielquellcode für Nested Table mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Dieser Aufruf ist wichtig, um innerhalb der ersten Tabelle eine verschachtelte Tabelle zu erstellen.
	// Ohne diesen Aufruf werden die unten eingefügten Zellen an die äußere Tabelle angehängt.
	builder.EndTable();
	// Gehen Sie zur ersten Zelle der äußeren Tabelle.
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine verschachtelte Tabelle in einem Word-Dokument erstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie verschachtelte Tabellen entsprechend Ihren spezifischen Anforderungen in Ihren Word-Dokumenten programmgesteuert erstellen.
