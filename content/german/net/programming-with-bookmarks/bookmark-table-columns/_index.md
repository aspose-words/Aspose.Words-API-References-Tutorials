---
title: Tabellenspalten im Word-Dokument mit Lesezeichen versehen
linktitle: Tabellenspalten im Word-Dokument mit Lesezeichen versehen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabellenspalte in einem Word-Dokument mit einem Lesezeichen versehen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/bookmark-table-columns/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Tabellenspalten mit Lesezeichen versehen“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Mit dieser Funktion können Sie eine bestimmte Spalte einer Tabelle in einem Word-Dokument mit einem Lesezeichen versehen und auf den Inhalt dieser Spalte zugreifen.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen der Tabelle

 Bevor wir ein Lesezeichen für eine Tabellenspalte erstellen können, müssen wir zunächst die Tabelle mit einem`DocumentBuilder`Objekt. In unserem Beispiel erstellen wir eine Tabelle mit zwei Zeilen und zwei Spalten:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Schritt 2: Spaltenlesezeichen erstellen

 Wir benutzen das`StartBookmark` Methode, um ein Lesezeichen in einer bestimmten Spalte der Tabelle zu erstellen. In unserem Beispiel verwenden wir den Namen „MyBookmark“ für das Lesezeichen:

```csharp
builder. StartBookmark("MyBookmark");
```

## Schritt 3: Zugriff auf den Spalteninhalt

 Wir gehen alle Lesezeichen im Dokument durch und zeigen ihre Namen an. Wenn ein Lesezeichen eine Spalte ist, greifen wir auf den Inhalt dieser Spalte über den Spaltenindex und die`GetText` Methode:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Beispielquellcode für Lesezeichentabellenspalten mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Erstellung eines Lesezeichens in einer Tabellenspalte mit Aspose.Words für .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Tabellenspalten mit Lesezeichen versehen“ von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um eine bestimmte Spalte einer Tabelle in einem Word-Dokument mit einem Lesezeichen zu versehen und zum Inhalt dieser Spalte zu springen.

### FAQs zu Lesezeichentabellenspalten in Word-Dokumenten

#### F: Was sind die Voraussetzungen, um die Funktion „Lesezeichen für Tabellenspalten“ in Aspose.Words für .NET zu verwenden?

A: Um die Funktion „Lesezeichen für Tabellenspalten“ in Aspose.Words für .NET verwenden zu können, benötigen Sie Grundkenntnisse der Programmiersprache C#. Sie benötigen außerdem eine .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

#### F: Wie erstelle ich mit Aspose.Words für .NET eine Tabelle mit Spalten in einem Word-Dokument?

 A: Um eine Tabelle mit Spalten in einem Word-Dokument mit Aspose.Words für .NET zu erstellen, können Sie ein`DocumentBuilder` Objekt zum Einfügen von Zellen und Inhalten in die Tabelle. Hier ist ein Beispielcode:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### F: Wie kann ich mit Aspose.Words für .NET eine Tabellenspalte mit einem Lesezeichen versehen?

 A: Um ein Lesezeichen für eine Tabellenspalte mit Aspose.Words für .NET zu erstellen, können Sie den`StartBookmark` Methode der`DocumentBuilder` Objekt, um das Lesezeichen in einer bestimmten Tabellenspalte zu starten. Hier ist ein Beispielcode:

```csharp
builder.StartBookmark("MyBookmark");
```

#### F: Wie greife ich mit Aspose.Words für .NET über ein Lesezeichen auf den Inhalt von Tabellenspalten zu?

A: Um mit Aspose.Words für .NET auf den Inhalt einer Tabellenspalte aus einem Lesezeichen zuzugreifen, können Sie alle Lesezeichen im Dokument durchlaufen, prüfen, ob ein Lesezeichen eine Spalte ist, und den Index der Spalte verwenden, um auf den Inhalt dieser Spalte zuzugreifen. Hier ist ein Beispielcode:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Machen Sie etwas mit dem Inhalt der Spalte...
         }
     }
}
```

#### F: Gibt es eine Begrenzung für die Anzahl der Spalten, die ich in einer Tabelle mit Spaltenlesezeichen erstellen kann?

A: Es gibt keine bestimmte Begrenzung für die Anzahl der Spalten, die Sie in einer Tabelle mit Spaltenlesezeichen mit Aspose.Words für .NET erstellen können. Die Begrenzung hängt hauptsächlich von den auf Ihrem System verfügbaren Ressourcen und den Spezifikationen des von Ihnen verwendeten Word-Dateiformats ab. Es wird jedoch empfohlen, nicht zu viele Spalten zu erstellen, da dies die Leistung und Lesbarkeit des endgültigen Dokuments beeinträchtigen kann.