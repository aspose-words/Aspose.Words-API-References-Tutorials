---
title: Wiederholen Sie Zeilen auf nachfolgenden Seiten
linktitle: Wiederholen Sie Zeilen auf nachfolgenden Seiten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Tabellenzeilen auf nachfolgenden Seiten in einem Word-Dokument wiederholen.
type: docs
weight: 10
url: /de/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET die Zeilen einer Tabelle auf nachfolgenden Seiten eines Word-Dokuments wiederholen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Zeilen anzugeben, die auf nachfolgenden Seiten Ihrer Tabelle in Ihren Word-Dokumenten wiederholt werden sollen.

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

## Schritt 3: Erstellen Sie die Tabelle mit wiederholten Zeilen
Als Nächstes erstellen wir eine Tabelle mit wiederholten Zeilen auf den folgenden Seiten. Verwenden Sie den folgenden Code:

```csharp
// Anfang der Tabelle
builder. StartTable();

// Konfiguration der ersten Zeilenparameter (Kopfzeilen)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Fügen Sie die erste Zelle der ersten Zeile ein
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Fügen Sie die zweite Zelle der ersten Zeile ein
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Konfigurieren Sie die Parameter der folgenden Zeilen
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Führen Sie eine Schleife aus, um die Zellen in die folgenden Zeilen einzufügen
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Ende des Tisches
builder. EndTable();
```

 Hier verwenden wir den Document Builder, um eine Tabelle mit zwei Kopfzeilen und mehreren Datenzeilen zu erstellen. Der`RowFormat.HeadingFormat`Parameter werden verwendet, um Kopfzeilen zu markieren, die auf nachfolgenden Seiten wiederholt werden sollen.

## Schritt 4: Speichern des geänderten Dokuments
Endlich USA

  Sie müssen das geänderte Dokument speichern, wobei die Kopfzeilen auf den folgenden Seiten der Tabelle wiederholt werden. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für Wiederholungszeilen auf nachfolgenden Seiten mit Aspose.Words für .NET 

```csharp
//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Zeilen einer Tabelle auf nachfolgenden Seiten eines Word-Dokuments wiederholt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie angeben, welche Zeilen entsprechend Ihren spezifischen Anforderungen in Ihren Word-Dokumenten wiederholt werden sollen.