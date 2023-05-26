---
title: Untangle radbokmärken
linktitle: Untangle radbokmärken
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du reder ut kapslade radbokmärken för att ta bort specifika rader utan att påverka andra bokmärken.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/untangle-row-bookmarks/
---

den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder Untangle Row Bookmarks-funktionen i Aspose.Words för .NET-biblioteket. Denna funktion gör det möjligt att sätta slutet av bokmärken på rader på samma rad som början på bokmärken.

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

	//Detta utför den anpassade uppgiften att sätta radbokmärkets ändar i samma rad som bokmärket börjar.
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