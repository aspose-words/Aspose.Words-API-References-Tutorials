---
title: Visa Göm bokmärken i Word-dokument
linktitle: Visa Göm bokmärken i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du visar eller döljer ett specifikt bokmärke i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/show-hide-bookmarks/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Show Hide Bookmarks i Aspose.Words for .NET-biblioteket. Denna funktion låter dig visa eller dölja ett specifikt bokmärke i Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Ladda dokumentet

 Vi använder`Document` klass för att ladda det befintliga dokumentet från en fil:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Steg 2: Visa eller dölj ett specifikt bokmärke

 Vi använder`ShowHideBookmarkedContent`funktion för att visa eller dölja ett specifikt bokmärke i dokumentet. Den här funktionen tar som parametrar dokumentet, namnet på bokmärket och en boolean för att indikera om bokmärket ska visas eller döljas:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Steg 3: Spara det ändrade dokumentet

 Vi använder`Save` metod för att spara det ändrade dokumentet till en fil:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Exempel på källkod för Show Hide Bookmarks med Aspose.Words för .NET

Här är det fullständiga exemplet på källkoden för att visa eller dölja ett specifikt bokmärke med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Visa göm bokmärken i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att visa eller dölja ett specifikt bokmärke i ett dokument.

### Vanliga frågor för att visa gömma bokmärken i word-dokument

#### F: Kan jag visa eller dölja flera bokmärken i samma dokument?

S: Ja, du kan visa eller dölja flera bokmärken i samma dokument genom att upprepa steg 2 och 3 för varje bokmärke du vill bearbeta.

#### F: Fungerar den medföljande koden med andra Word-dokumentformat, som .doc eller .docm?

S: Ja, den medföljande koden fungerar med olika Word-dokumentformat som stöds av Aspose.Words, såsom .doc och .docm. Se bara till att använda rätt filnamn och sökväg när du laddar och sparar dokumentet.

#### F: Hur kan jag visa ett dolt bokmärke igen?

 S: För att visa ett dolt bokmärke igen måste du använda detsamma`ShowHideBookmarkedContent` funktion som skickar värdet`true` för den booleska parametern som anger om bokmärket ska visas eller döljas.

#### F: Kan jag använda villkor för att visa eller dölja bokmärken baserat på sammanslagningsfältsvärden i dokumentet?

 S: Ja, du kan använda villkor och slå samman fältvärden för att avgöra om ett bokmärke ska visas eller döljas. Du kan anpassa koden för`ShowHideBookmarkedContent` funktion för att ta hänsyn till lämpliga villkor och värden.

#### F: Hur kan jag ta bort ett bokmärke i ett Word-dokument med Aspose.Words för .NET?

 S: För att ta bort ett bokmärke i ett Word-dokument med Aspose.Words för .NET, kan du använda`RemoveBookmarks` metod för`Document` klass. Här är en exempelkod:

```csharp
doc.RemoveBookmarks("BookmarkName");
```