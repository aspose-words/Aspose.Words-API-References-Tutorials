---
title: Bokmärk tabellkolumner i Word-dokument
linktitle: Bokmärk tabellkolumner i Word-dokument
second_title: Aspose.Words Document Processing API
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

 Innan vi skapar ett bokmärke på en tabellkolumn måste vi först skapa tabellen med hjälp av en`DocumentBuilder`objekt. I vårt exempel skapar vi en tabell med två rader och två kolumner:

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

 Vi använder`StartBookmark` metod för att skapa ett bokmärke på en specifik kolumn i tabellen. I vårt exempel använder vi namnet "Mitt bokmärke" för bokmärket:

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

### Vanliga frågor om bokmärkestabellkolumner i word-dokument

#### F: Vilka är förutsättningarna för att använda funktionen "Bokmärken för tabellkolumner" i Aspose.Words för .NET?

S: För att använda funktionen "Bokmärken för tabellkolumner" i Aspose.Words för .NET måste du ha grundläggande kunskaper i C#-språket. Du behöver också en .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

#### F: Hur skapar man en tabell med kolumner i ett Word-dokument med Aspose.Words för .NET?

 S: För att skapa en tabell med kolumner i ett Word-dokument med Aspose.Words för .NET, kan du använda en`DocumentBuilder` objekt för att infoga celler och innehåll i tabellen. Här är en exempelkod:

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

#### F: Hur bokmärker man en tabellkolumn med Aspose.Words för .NET?

 S: För att skapa ett bokmärke i en tabellkolumn med Aspose.Words för .NET kan du använda`StartBookmark` metod för`DocumentBuilder` objekt för att starta bokmärket på en specifik tabellkolumn. Här är en exempelkod:

```csharp
builder.StartBookmark("MyBookmark");
```

#### F: Hur får man tillgång till tabellkolumnsinnehåll från bokmärke med Aspose.Words för .NET?

S: För att komma åt innehållet i en tabellkolumn från ett bokmärke med Aspose.Words för .NET kan du gå igenom alla bokmärken i dokumentet, kontrollera om ett bokmärke är en kolumn och använda kolumnindex för att komma åt innehållet i den kolumnen. Här är en exempelkod:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Gör något med innehållet i spalten...
         }
     }
}
```

#### F: Finns det en gräns för antalet kolumner jag kan skapa i en tabell med kolumnbokmärken?

S: Det finns ingen specifik gräns för antalet kolumner du kan skapa i en tabell med kolumnbokmärken med Aspose.Words för .NET. Gränsen beror huvudsakligen på de resurser som finns tillgängliga på ditt system och specifikationerna för det Word-filformat du använder. Det rekommenderas dock att inte skapa ett alltför stort antal kolumner, eftersom detta kan påverka slutdokumentets prestanda och läsbarhet.