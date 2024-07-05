---
title: Zeilen auf nachfolgenden Seiten wiederholen
linktitle: Zeilen auf nachfolgenden Seiten wiederholen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Tabellenzeilen auf nachfolgenden Seiten in einem Word-Dokument wiederholen.
type: docs
weight: 10
url: /de/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

In diesem Tutorial lernen wir, wie man die Zeilen einer Tabelle auf den nachfolgenden Seiten eines Word-Dokuments mit Aspose.Words für .NET wiederholt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Zeilen angeben, die auf den nachfolgenden Seiten Ihrer Tabelle in Ihren Word-Dokumenten wiederholt werden sollen.

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

## Schritt 3: Erstellen der Tabelle mit wiederholten Zeilen
Als Nächstes erstellen wir eine Tabelle mit wiederholten Zeilen auf den nachfolgenden Seiten. Verwenden Sie den folgenden Code:

```csharp
// Beginn der Tabelle
builder. StartTable();

// Konfiguration der Parameter der ersten Zeile (Kopfzeilen)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Fügt die erste Zelle der ersten Zeile ein
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Einfügen der zweiten Zelle der ersten Zeile
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Konfigurieren Sie die Parameter der folgenden Zeilen
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Schleife zum Einfügen der Zellen in die folgenden Zeilen
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Ende der Tabelle
builder. EndTable();
```

 Hier verwenden wir den Dokumentgenerator, um eine Tabelle mit zwei Kopfzeilen und mehreren Datenzeilen zu erstellen. Die`RowFormat.HeadingFormat`Parameter werden verwendet, um Kopfzeilen zu markieren, die auf nachfolgenden Seiten wiederholt werden sollen.

## Schritt 4: Speichern des geänderten Dokuments
Endlich USA

  Sie müssen das geänderte Dokument mit den auf den nachfolgenden Seiten der Tabelle wiederholten Kopfzeilen speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispiel-Quellcode für „Zeilen auf nachfolgenden Seiten wiederholen“ mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
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
In diesem Tutorial haben wir gelernt, wie man die Zeilen einer Tabelle mit Aspose.Words für .NET auf den folgenden Seiten eines Word-Dokuments wiederholt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie angeben, welche Zeilen entsprechend Ihren spezifischen Anforderungen in Ihren Word-Dokumenten wiederholt werden sollen.