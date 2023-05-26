---
title: Få tillgång till bokmärken
linktitle: Få tillgång till bokmärken
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du kommer åt bokmärken i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/access-bookmarks/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder Access Bookmarks-funktionen i Aspose.Words för .NET-biblioteket. Den här funktionen ger åtkomst till specifika bokmärken i ett Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Ladda dokumentet

 Innan vi börjar komma åt bokmärken måste vi ladda ett Word-dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt som anger sökvägen till dokumentfilen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Steg 2: Tillgång till bokmärken

När dokumentet har laddats kan vi komma åt bokmärkena i dokumentet. Det finns två sätt att komma åt bokmärken: genom index och med namn.

- Åtkomst via index: I vårt exempel använder vi index 0 för att komma åt dokumentets första bokmärke:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Access by name: I vårt exempel använder vi namnet "MyBookmark3" för att komma åt ett specifikt bokmärke i dokumentet:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Exempel på källkod för Access Bookmarks med Aspose.Words för .NET

Här är det fullständiga exemplet på källkoden för att visa åtkomst till bokmärken med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Efter index:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Vid namn:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder Access Bookmarks-funktionen i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att ladda upp ett dokument och komma åt bokmärken med hjälp av index och namn.