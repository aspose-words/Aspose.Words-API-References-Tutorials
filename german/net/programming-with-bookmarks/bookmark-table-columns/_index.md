---
title: Lesezeichen für Tabellenspalten setzen
linktitle: Lesezeichen für Tabellenspalten setzen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabellenspalte in einem Word-Dokument mit einem Lesezeichen versehen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/bookmark-table-columns/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Bookmark Table Columns“ in der Aspose.Words for .NET-Bibliothek verwendet wird. Mit dieser Funktion können Sie eine bestimmte Spalte einer Tabelle in einem Word-Dokument mit einem Lesezeichen versehen und auf den Inhalt dieser Spalte zugreifen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen der Tabelle

 Bevor wir ein Lesezeichen für eine Tabellenspalte erstellen, müssen wir zunächst die Tabelle mit a erstellen`DocumentBuilder` Objekt. In unserem Beispiel erstellen wir eine Tabelle mit zwei Zeilen und zwei Spalten:

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

## Schritt 2: Erstellen des Spaltenlesezeichens

 Wir benutzen das`StartBookmark`Methode zum Erstellen eines Lesezeichens für eine bestimmte Spalte der Tabelle. In unserem Beispiel verwenden wir für das Lesezeichen den Namen „MyBookmark“:

```csharp
builder. StartBookmark("MyBookmark");
```

## Schritt 3: Greifen Sie auf den Spalteninhalt zu

 Wir gehen alle Lesezeichen im Dokument durch und zeigen ihre Namen an. Wenn es sich bei einem Lesezeichen um eine Spalte handelt, greifen wir mithilfe des Spaltenindex und des auf den Inhalt dieser Spalte zu`GetText` Methode:

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

Hier ist der vollständige Beispielquellcode, um das Erstellen eines Lesezeichens für eine Tabellenspalte mit Aspose.Words für .NET zu demonstrieren:

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

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Bookmark Table Columns“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um eine bestimmte Spalte einer Tabelle in einem Word-Dokument mit einem Lesezeichen zu versehen und zum Inhalt dieser Spalte zu springen.