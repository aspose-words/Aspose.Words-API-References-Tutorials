---
title: Reda ut i Word-dokument
linktitle: Reda ut i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du reder ut i word-dokument kapslade bokmärken i intilliggande tabellrader med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/untangle/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder Untangle-funktionen i Aspose.Words för .NET-biblioteket. Den här funktionen reder ut kapslade bokmärken som finns i intilliggande tabellrader.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Bläddra i dokumentbokmärken

Vi använder en foreach loop för att gå igenom alla bokmärken som finns i dokumentet:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Kod för hantering av bokmärken här
}
```

## Steg 2: Hämta överordnade rader från bokmärken

 Vi använder`GetAncestor`metoder för att hämta de överordnade raderna för bokmärkets start- och slutnoder:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Steg 3: Lossa kapslade bokmärken

Om båda överordnade raderna hittas och bokmärket börjar och slutar på intilliggande rader, flyttar vi bokmärkets slutnod till slutet av det sista stycket i den sista cellen i den översta raden:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Exempel på källkod för Untangle med Aspose.Words för .NET

Här är det fullständiga källkodsexemplet för att reda ut kapslade bokmärken med Aspose.Words för .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Hämta den överordnade raden för både bokmärkets och bokmärkets slutnod.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Om båda raderna upptäcks som okej och bokmärkets början och slut finns i intilliggande rader,
		// flytta bokmärkets slutnod till slutet av det sista stycket i den översta radens sista cell.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder Untangle-funktionen i Aspose.Words för .NET. Vi har följt en steg-för-steg-guide för att reda ut kapslade bokmärken i intilliggande tabellrader.

### FAQ's

#### F: Fungerar Untangle-funktionen bara med kapslade bokmärken i intilliggande tabellrader?

S: Ja, funktionen Untangle är utformad speciellt för att reda ut kapslade bokmärken som finns i intilliggande tabellrader. Om bokmärkena inte finns på intilliggande rader kommer denna funktion inte att vara tillämplig.

#### F: Hur kan jag identifiera kapslade bokmärken i mitt Word-dokument?

S: Du kan identifiera kapslade bokmärken genom att gå igenom bokmärkena i dokumentet och kontrollera om startbokmärket och slutbokmärket finns i intilliggande tabellrader. Du kan använda källkoden i den här artikeln som utgångspunkt för att implementera den här funktionen.

#### F: Modifierar Unscramble-funktionen innehållet i originaldokumentet?

S: Ja, funktionen Untangle modifierar originaldokumentet genom att flytta bokmärkets slutnod till slutet av det sista stycket i den sista cellen i den översta raden. Se till att spara en säkerhetskopia av dokumentet innan du använder den här funktionen.

#### F: Hur kan jag reda ut kapslade bokmärken i andra typer av dokumentelement, till exempel avsnitt eller stycken?

S: Funktionen Untangle som presenteras i den här artikeln är speciellt utformad för att reda ut kapslade bokmärken i intilliggande tabellrader. Om du vill reda ut kapslade bokmärken i andra dokumentelement måste du anpassa koden därefter och använda lämpliga metoder för att komma åt de önskade elementen.

#### F: Finns det några andra metoder för att reda ut kapslade bokmärken i ett Word-dokument med Aspose.Words för .NET?

 S: Metoden som presenteras i den här artikeln är en vanlig metod för att reda ut kapslade bokmärken i intilliggande tabellrader. Det kan dock finnas andra tillvägagångssätt eller tekniker beroende på de specifika behoven i ditt projekt. Du kan kolla in[Aspose.Words för .NET API-referenser](https://reference.aspose.com/words/net/) för att ytterligare utforska de tillgängliga funktionerna.