---
title: Visa Göm bokmärken
linktitle: Visa Göm bokmärken
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du visar eller döljer ett specifikt bokmärke i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/show-hide-bookmarks/
---

den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Show Hide Bookmarks i Aspose.Words for .NET-biblioteket. Med den här funktionen kan du visa eller dölja ett specifikt bokmärke i ett dokument.

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

 Vi använder`ShowHideBookmarkedContent` funktion för att visa eller dölja ett specifikt bokmärke i dokumentet. Den här funktionen tar som parametrar dokumentet, namnet på bokmärket och en boolean för att indikera om bokmärket ska visas eller döljas:

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

den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Visa göm bokmärken i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att visa eller dölja ett specifikt bokmärke i ett dokument.