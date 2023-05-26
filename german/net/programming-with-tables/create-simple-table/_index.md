---
title: Erstellen Sie eine einfache Tabelle
linktitle: Erstellen Sie eine einfache Tabelle
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine einfache Tabelle in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-tables/create-simple-table/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine einfache Tabelle in einem Word-Dokument erstellt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, benutzerdefinierte Tabellen in Ihren Word-Dokumenten programmgesteuert zu erstellen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentengenerators
Um mit dem Aufbau der Tabelle zu beginnen, müssen wir ein neues Dokument erstellen und den Document Builder initialisieren. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und initialisieren Sie den Dokumentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Aufbau des Arrays
Als Nächstes erstellen wir die Tabelle mit den vom Document Builder bereitgestellten Methoden. Verwenden Sie den folgenden Code:

```csharp
// Beginnen Sie mit dem Aufbau des Arrays
builder. StartTable();

// Bau der ersten Zelle der ersten Reihe
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Bau der zweiten Zelle der ersten Reihe
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Rufen Sie die folgende Methode auf, um die erste Zeile zu beenden und eine neue Zeile zu beginnen
builder. EndRow();

// Aufbau der ersten Zelle der zweiten Reihe
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Bau der zweiten Zelle der zweiten Reihe
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Rufen Sie die nächste Methode auf, um die zweite Zeile zu beenden
builder. EndRow();

// Zeigt an, dass der Bau des Tisches abgeschlossen ist
builder. EndTable();
```

 Hier verwenden wir den Document Builder, um die Tabelle Schritt für Schritt aufzubauen. Wir beginnen mit einem Anruf`StartTable()` um die Tabelle zu initialisieren, dann verwenden`InsertCell()` Zellen einfügen und`Write()` um Inhalt zu jeder Zelle hinzuzufügen. Wir benützen auch`EndRow()` um eine Zeile zu beenden und eine neue Zeile zu beginnen. Zum Schluss rufen wir an`EndTable()` um anzuzeigen, dass die Tabellenkonstruktion abgeschlossen ist.

## Schritt 4: Speichern Sie das Dokument
Schließlich müssen wir sparen

  das Dokument mit der erstellten Tabelle. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das Dokument
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode zum Erstellen einer einfachen Tabelle mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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
	//Signalisieren Sie, dass wir mit dem Aufbau der Tabelle fertig sind.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine einfache Tabelle in einem Word-Dokument erstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie benutzerdefinierte Tabellen in Ihren Word-Dokumenten programmgesteuert erstellen. Mit dieser Funktion können Sie Ihre Daten strukturiert und übersichtlich formatieren und organisieren.