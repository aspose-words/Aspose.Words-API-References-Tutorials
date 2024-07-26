---
title: Einfache Tabelle erstellen
linktitle: Einfache Tabelle erstellen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine einfache Tabelle in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-tables/create-simple-table/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine einfache Tabelle in einem Word-Dokument erstellt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie programmgesteuert benutzerdefinierte Tabellen in Ihren Word-Dokumenten erstellen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentgenerators
Um mit dem Erstellen der Tabelle zu beginnen, müssen wir ein neues Dokument erstellen und den Dokumentgenerator initialisieren. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Erstellen Sie das Dokument und initialisieren Sie den Dokumentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Erstellen des Arrays
Als Nächstes erstellen wir die Tabelle mit den vom Dokument-Generator bereitgestellten Methoden. Verwenden Sie den folgenden Code:

```csharp
// Beginnen Sie mit der Array-Konstruktion
builder. StartTable();

// Aufbau der ersten Zelle der ersten Reihe
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Aufbau der zweiten Zelle der ersten Reihe
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

// Rufen Sie die folgende Methode auf, um die erste Zeile zu beenden und eine neue Zeile zu beginnen
builder. EndRow();

// Aufbau der ersten Zelle der zweiten Reihe
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Aufbau der zweiten Zelle der zweiten Reihe
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Rufen Sie die nächste Methode auf, um die zweite Zeile zu beenden
builder. EndRow();

// Hinweis, dass der Bau des Tisches abgeschlossen ist
builder. EndTable();
```

 Hier verwenden wir den Dokumentgenerator, um die Tabelle Schritt für Schritt aufzubauen. Wir beginnen mit dem Aufruf`StartTable()` um die Tabelle zu initialisieren, dann verwenden Sie`InsertCell()` zum Einfügen von Zellen und`Write()` um jeder Zelle Inhalt hinzuzufügen. Wir verwenden auch`EndRow()` um eine Zeile zu beenden und eine neue Zeile zu beginnen. Schließlich rufen wir`EndTable()` um anzuzeigen, dass der Tabellenaufbau abgeschlossen ist.

## Schritt 4: Speichern Sie das Dokument
Schließlich müssen wir sparen

  das Dokument mit der erstellten Tabelle. Verwenden Sie den folgenden Code:

```csharp
// Speichern des Dokuments
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode zum Erstellen einer einfachen Tabelle mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Beginnen Sie mit dem Aufbau der Tabelle.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Bauen Sie die zweite Zelle.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Rufen Sie die folgende Methode auf, um die Zeile zu beenden und eine neue Zeile zu beginnen.
	builder.EndRow();
	// Bauen Sie die erste Zelle der zweiten Reihe.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Bauen Sie die zweite Zelle.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	// Signal, dass wir mit dem Erstellen der Tabelle fertig sind.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine einfache Tabelle in einem Word-Dokument erstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie programmgesteuert benutzerdefinierte Tabellen in Ihren Word-Dokumenten erstellen. Mit dieser Funktion können Sie Ihre Daten strukturiert und übersichtlich formatieren und organisieren.