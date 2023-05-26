---
title: Ta bort innehåll i sidhuvud
linktitle: Ta bort innehåll i sidhuvud
second_title: Aspose.Words för .NET API Referens
description: den här handledningen lär du dig hur du tar bort sidhuvud och sidfotsinnehåll från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-section/delete-header-footer-content/
---

I den här handledningen kommer vi att visa dig hur du tar bort sidhuvud och sidfotsinnehåll från Word-dokument med Aspose.Words-biblioteket för .NET. Att ta bort innehåll från sidhuvuden och sidfötter kan vara användbart när du vill återställa eller ta bort dessa element från ditt dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som innehåller sidhuvuden och sidfötter som du vill ta bort

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet och gå till avsnittet
 Därefter laddar vi Word-dokumentet i en instans av`Document` klass. Vi kommer åt den första delen av dokumentet med index 0.

```csharp
//Ladda dokumentet
Document doc = new Document(dataDir + "Document.docx");

// Gå till avsnittet
Section section = doc.Sections[0];
```

## Steg 3: Ta bort sidhuvud och sidfotsinnehåll
 För att ta bort innehållet i sidhuvudet och sidfoten från avsnittet använder vi`ClearHeadersFooters` metod.

```csharp
section.ClearHeadersFooters();
```

### Exempel på källkod för Ta bort innehåll i sidhuvud med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Slutsats
den här handledningen har vi sett hur du tar bort sidhuvud och sidfotsinnehåll från ett Word-dokument med Aspose.Words för .NET. Genom att ta bort innehåll från sidhuvuden och sidfötter kan du återställa eller ta bort de specifika elementen från ditt dokument. Känn dig fri att anpassa och använda den här funktionen efter dina specifika behov.
