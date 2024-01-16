---
title: Maak een bladwijzer van tabelkolommen in een Word-document
linktitle: Maak een bladwijzer van tabelkolommen in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een bladwijzer kunt maken voor een tabelkolom in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/bookmark-table-columns/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Bladwijzertabelkolommen in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Met deze functie kunt u een bladwijzer maken voor een specifieke kolom van een tabel in een Word-document en toegang krijgen tot de inhoud van die kolom.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: De tabel maken

 Voordat we een bladwijzer voor een tabelkolom maken, moeten we eerst de tabel maken met behulp van a`DocumentBuilder`voorwerp. In ons voorbeeld maken we een tabel met twee rijen en twee kolommen:

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

## Stap 2: De kolombladwijzer maken

 Wij gebruiken de`StartBookmark` methode om een bladwijzer voor een specifieke kolom van de tabel te maken. In ons voorbeeld gebruiken we de naam "MyBookmark" voor de bladwijzer:

```csharp
builder. StartBookmark("MyBookmark");
```

## Stap 3: Toegang tot de kolominhoud

 We doorlopen alle bladwijzers in het document en geven hun namen weer. Als een bladwijzer een kolom is, hebben we toegang tot de inhoud van die kolom met behulp van de kolomindex en de`GetText` methode:

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

### Voorbeeldbroncode voor bladwijzertabelkolommen met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om te demonstreren hoe u een bladwijzer in een tabelkolom maakt met behulp van Aspose.Words voor .NET:

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

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Bookmark Table Columns van Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om een specifieke kolom van een tabel in een Word-document van een bladwijzer te voorzien en naar de inhoud van die kolom te gaan.

### Veelgestelde vragen over bladwijzertabelkolommen in een Word-document

#### Vraag: Wat zijn de vereisten voor het gebruik van de functie "Bladwijzers voor tabelkolommen" in Aspose.Words voor .NET?

A: Om de functie "Bladwijzers voor tabelkolommen" in Aspose.Words voor .NET te gebruiken, hebt u basiskennis van de C#-taal nodig. U hebt ook een .NET-ontwikkelomgeving nodig waarin de Aspose.Words-bibliotheek is geïnstalleerd.

#### Vraag: Hoe maak ik een tabel met kolommen in een Word-document met Aspose.Words voor .NET?

 A: Om een tabel met kolommen in een Word-document te maken met Aspose.Words voor .NET, kunt u een`DocumentBuilder` object om cellen en inhoud in de tabel in te voegen. Hier is een voorbeeldcode:

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

#### Vraag: Hoe kan ik een tabelkolom bookmarken met Aspose.Words voor .NET?

 A: Om een bladwijzer voor een tabelkolom te maken met behulp van Aspose.Words voor .NET, kunt u de`StartBookmark` werkwijze van de`DocumentBuilder` object om de bladwijzer op een specifieke tabelkolom te starten. Hier is een voorbeeldcode:

```csharp
builder.StartBookmark("MyBookmark");
```

#### Vraag: Hoe krijg ik toegang tot de inhoud van tabelkolommen vanuit een bladwijzer met Aspose.Words voor .NET?

A: Om toegang te krijgen tot de inhoud van een tabelkolom vanuit een bladwijzer met behulp van Aspose.Words voor .NET, kunt u door alle bladwijzers in het document bladeren, controleren of een bladwijzer een kolom is en de index van de kolom gebruiken om toegang te krijgen tot de inhoud van die kolom. Hier is een voorbeeldcode:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Doe iets met de inhoud van de kolom...
         }
     }
}
```

#### Vraag: Is er een limiet aan het aantal kolommen dat ik kan maken in een tabel met kolombladwijzers?

A: Er is geen specifieke limiet voor het aantal kolommen dat u kunt maken in een tabel met kolombladwijzers met behulp van Aspose.Words voor .NET. De limiet hangt vooral af van de beschikbare bronnen op uw systeem en de specificaties van het Word-bestandsformaat dat u gebruikt. Het wordt echter aanbevolen om geen buitensporig groot aantal kolommen te maken, omdat dit de prestaties en leesbaarheid van het uiteindelijke document kan beïnvloeden.