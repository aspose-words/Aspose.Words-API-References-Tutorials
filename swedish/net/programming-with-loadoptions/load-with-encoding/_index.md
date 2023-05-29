---
title: Ladda med kodning
linktitle: Ladda med kodning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du laddar ett dokument med en specificerad kodning med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-loadoptions/load-with-encoding/
---
När man arbetar med textdokument i en C#-applikation är det viktigt att kunna ladda dem korrekt genom att ange rätt kodning. Med Aspose.Words-biblioteket för .NET kan du enkelt ladda textdokument med önskad kodning med hjälp av laddningsalternativen LoadOptions. I den här steg-för-steg-guiden går vi igenom hur du använder Aspose.Words för .NET C#-källkod för att ladda ett textdokument med den angivna kodningen med hjälp av LoadOptions laddningsalternativ.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Konfigurera laddningsalternativ

Det första steget är att konfigurera laddningsalternativen för vårt textdokument. Använd klassen LoadOptions för att ange laddningsparametrar. I vårt fall måste vi ställa in Encoding-egenskapen till önskad kodning, till exempel Encoding.UTF7 för UTF-7-kodning. Så här gör du:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };
```

Vi skapar ett nytt LoadOptions-objekt och sätter egenskapen Encoding till Encoding.UTF7 för att specificera UTF-7-kodning.

## Laddar dokument med angiven kodning

Nu när vi har konfigurerat laddningsalternativen kan vi ladda dokumentet med klassen Document och ange laddningsalternativen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

I det här exemplet laddar vi dokumentet "Encoded in UTF-7.txt" som finns i dokumentkatalogen med de angivna laddningsalternativen.

### Exempel på källkod för LoadOptions med "Load With Encoding" funktionalitet med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurera laddningsalternativ med önskad kodning (UTF-7)
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };

// Ladda dokumentet med den angivna kodningen
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

## Slutsats

den här guiden förklarade vi hur man laddar ett textdokument med en specificerad kodning med hjälp av Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Att ladda textdokument med rätt kodning säkerställer korrekt och korrekt läsning av innehållet i din applikation.