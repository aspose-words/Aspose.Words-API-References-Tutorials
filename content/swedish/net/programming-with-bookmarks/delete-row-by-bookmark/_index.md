---
title: Ta bort rad efter bokmärke i Word-dokument
linktitle: Ta bort rad efter bokmärke i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du tar bort en tabellrad baserat på ett specifikt bokmärke i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/delete-row-by-bookmark/
---

I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Ta bort rad efter bokmärke i Aspose.Words för .NET-biblioteket. Denna funktion låter dig ta bort en tabellrad baserat på ett specifikt bokmärke i Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skaffa bokmärket

 Vi använder`Bookmarks` egenskapen för dokumentintervallet för att få det specifika bokmärke vi vill använda för att ta bort tabellraden:

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

### Vanliga frågor för att ta bort rad för bokmärke i Word-dokument

#### F: Kan jag ta bort flera rader med samma bokmärke?

S: Ja, du kan ta bort flera rader med samma bokmärke. Du måste dock hantera logiken i din kod för att bestämma antalet rader som ska raderas och göra nödvändiga justeringar av kodavsnittet som tillhandahålls.

#### F: Vad händer om bokmärket inte finns i dokumentet?

S: Om det angivna bokmärket inte finns i dokumentet kommer kodavsnittet att returnera ett nullvärde för bokmärkesobjektet. Därför måste du hantera detta scenario i din kod genom att lägga till lämpliga kontroller innan du försöker ta bort tabellraden.

#### F: Är Aspose.Words-biblioteket gratis att använda?

 S: Aspose.Words-biblioteket är ett kommersiellt bibliotek och du kan behöva en giltig licens för att använda det i dina projekt. Du kan besöka[Aspose.Words för .NET API-referenser](https://reference.aspose.com/words/net/) för att lära dig mer om deras licensalternativ och priser.

#### F: Kan jag ta bort rader från en tabell i en specifik del av Word-dokumentet?

S: Ja, du kan ta bort rader från en tabell i en specifik del av ett Word-dokument. Du kan ändra kodavsnittet för att rikta in dig på ett specifikt avsnitt genom att använda lämpligt intervall eller bokmärke inom det avsnittet.