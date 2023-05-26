---
title: Bokmärk tabellkolumner
linktitle: Bokmärk tabellkolumner
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du bokmärker en tabellkolumn i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/bookmark-table-columns/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Bookmark Table Columns i Aspose.Words for .NET-biblioteket. Med den här funktionen kan du bokmärka en specifik kolumn i en tabell i ett Word-dokument och komma åt innehållet i den kolumnen.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa tabellen

 Innan vi skapar ett bokmärke på en tabellkolumn måste vi först skapa tabellen med hjälp av en`DocumentBuilder` objekt. I vårt exempel skapar vi en tabell med två rader och två kolumner:

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

## Steg 2: Skapa kolumnbokmärket

 Vi använder`StartBookmark`metod för att skapa ett bokmärke på en specifik kolumn i tabellen. I vårt exempel använder vi namnet "Mitt bokmärke" för bokmärket:

```csharp
builder. StartBookmark("MyBookmark");
```

## Steg 3: Gå till kolumninnehållet

 Vi går igenom alla bokmärken i dokumentet och visar deras namn. Om ett bokmärke är en kolumn kommer vi åt innehållet i den kolumnen med hjälp av kolumnindex och`GetText` metod:

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

### Exempel på källkod för bokmärkestabellkolumner med Aspose.Words för .NET

Här är den fullständiga källkoden för att demonstrera att skapa ett bokmärke i en tabellkolumn med Aspose.Words för .NET:

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

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Bokmärkestabellkolumner i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att bokmärka en specifik kolumn i en tabell i ett Word-dokument och hoppa till innehållet i den kolumnen.