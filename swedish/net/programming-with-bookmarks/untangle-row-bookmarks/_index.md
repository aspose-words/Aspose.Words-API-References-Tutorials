---
title: Reda ut radbokmärken i Word-dokument
linktitle: Reda ut radbokmärken i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du reder ut kapslade radbokmärken i Word-dokument för att ta bort specifika rader utan att påverka andra bokmärken.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/untangle-row-bookmarks/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder Untangle Row Bookmarks-funktionen i Aspose.Words för .NET-biblioteket. Denna funktion gör det möjligt att sätta slutet av bokmärken på rader på samma rad som början på bokmärken.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Ladda dokumentet

 Vi använder`Document` klass för att ladda det befintliga dokumentet från en fil:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Steg 2: Rensa upp linjebokmärken

 Vi använder`Untangle` funktion för att reda ut bokmärken från rader. Den här funktionen utför den anpassade uppgiften att placera bokmärkesändarna på rader på samma rad som bokmärket börjar:

```csharp
Untangle(doc);
```

## Steg 3: Ta bort rad för bokmärke

 Vi använder`DeleteRowByBookmark` funktion för att ta bort en specifik rad efter dess bokmärke:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Steg 4: Kontrollera integriteten för andra bokmärken

Vi verifierar att de andra bokmärkena inte har skadats genom att kontrollera om slutet av bokmärket fortfarande finns kvar:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Exempel på källkod för Untangle Row Bookmarks med Aspose.Words för .NET**

Här är den fullständiga källkoden för att reda ut bokmärken från rader med Aspose.Words för .NET:


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	// Detta utför den anpassade uppgiften att sätta radbokmärkets ändar i samma rad som bokmärket börjar.
	Untangle(doc);

	// Nu kan vi enkelt ta bort rader efter ett bokmärke utan att skada någon annan rads bokmärken.
	DeleteRowByBookmark(doc, "ROW2");

	// Detta är bara för att kontrollera att det andra bokmärket inte var skadat.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder Untangle Row Bookmarks-funktionen i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att reda ut radbokmärken och ta bort en specifik rad utan att skada andra bokmärken.

### Vanliga frågor för att reda ut radbokmärken i word-dokument

#### F: Fungerar Unscramble Row Bookmarks endast med radbokmärken i tabeller?

S: Ja, funktionen Untangle Row Bookmarks är speciellt utformad för att reda ut radbokmärken som finns i tabeller. Den här funktionen kan användas för att bearbeta linjebokmärken i arrayer och säkerställa att bokmärkesändarna ligger på samma rad som bokmärkesstarter.

#### F: Modifierar funktionen Unscramble Line Bookmarks innehållet i originaldokumentet?

S: Ja, funktionen Unscramble line bookmarks modifierar originaldokumentet genom att flytta ändarna på radbokmärken för att placera dem på samma rad som början av bokmärken. Se till att spara en säkerhetskopia av dokumentet innan du använder den här funktionen.

#### F: Hur kan jag identifiera linjebokmärken i mitt Word-dokument?

S: Radbokmärken används vanligtvis i tabeller för att markera specifika avsnitt. Du kan identifiera radbokmärken genom att bläddra igenom bokmärkena i dokumentet och kontrollera om bokmärkena finns i tabellrader.

#### F: Är det möjligt att reda ut radbokmärken i icke-intilliggande tabeller?

S: Funktionen Untangle Row Bookmarks som presenteras i den här artikeln är utformad för att reda ut radbokmärken i intilliggande tabeller. För att reda ut radbokmärken i icke-intilliggande tabeller kan ytterligare justeringar av koden krävas beroende på dokumentets struktur.

#### F: Vilka andra manipulationer kan jag utföra på radbokmärken när de har lösts upp?

S: När linjens bokmärken är uppradade kan du utföra olika manipulationer efter behov. Detta kan inkludera att redigera, ta bort eller lägga till innehåll på bokmärkta rader. Var noga med att hantera radbokmärken med omsorg för att undvika oönskad påverkan på resten av dokumentet.