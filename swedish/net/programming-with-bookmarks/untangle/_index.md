---
title: Reda ut
linktitle: Reda ut
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du reder ut kapslade bokmärken i intilliggande tabellrader med Aspose.Words för .NET.
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

 Vi använder`GetAncestor` metoder för att hämta de överordnade raderna för bokmärkets start- och slutnoder:

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