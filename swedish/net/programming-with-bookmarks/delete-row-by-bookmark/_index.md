---
title: Ta bort rad efter bokmärke
linktitle: Ta bort rad efter bokmärke
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du tar bort en tabellrad baserat på ett specifikt bokmärke i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/delete-row-by-bookmark/
---

I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Ta bort rad efter bokmärke i Aspose.Words för .NET-biblioteket. Den här funktionen låter dig ta bort en tabellrad baserat på ett specifikt bokmärke i ett dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skaffa bokmärket

 Vi använder`Bookmarks`egenskapen för dokumentintervallet för att få det specifika bokmärke vi vill använda för att ta bort tabellraden:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Steg 2: Ta bort tabellraden

 Vi använder`GetAncestor` metod för att få`Row` skriv bokmärkets överordnade element. Därefter använder vi`Remove` metod för att ta bort tabellraden:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Exempel på källkod för Ta bort rad efter bokmärke med Aspose.Words för .NET

Här är det fullständiga källkodsexemplet för att demonstrera radering av en tabellrad baserat på ett specifikt bokmärke med Aspose.Words för .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Slutsats

I den här artikeln har vi utforskat C#-källkoden för att förstå hur man använder funktionen Ta bort rad efter bokmärke i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att ta bort en tabellrad baserat på ett specifikt bokmärke i ett dokument.