---
title: Använd Temp-mappen
linktitle: Använd Temp-mappen
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder en tillfällig mapp när du laddar upp dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-loadoptions/use-temp-folder/
---

När du arbetar med Word-dokument i en C#-applikation kan det vara nödvändigt att använda en temporär mapp för att lagra temporära filer som genererats under dokumentbehandlingen. Med Aspose.Words-biblioteket för .NET kan du enkelt ange en tillfällig mapp med laddningsalternativen LoadOptions. I den här steg-för-steg-guiden kommer vi att visa dig hur du använder Aspose.Words för .NET C#-källkod för att ladda ett dokument med hjälp av en temporär mapp som anges med laddningsalternativen LoadOptions.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Konfigurera laddningsalternativ

Det första steget är att konfigurera laddningsalternativen för vårt dokument. Använd klassen LoadOptions för att ange laddningsparametrar. I vårt fall måste vi ställa in TempFolder-egenskapen till sökvägen till den önskade temporära mappen. Så här gör du:

```csharp
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };
```

Vi skapar ett nytt LoadOptions-objekt och ställer in TempFolder-egenskapen till sökvägen till den önskade temporära mappen.

## Ladda upp dokument med den angivna temporära mappen

Nu när vi har konfigurerat laddningsalternativen kan vi ladda dokumentet med klassen Document och ange laddningsalternativen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

I det här exemplet laddar vi dokumentet "Document.docx" som finns i dokumentkatalogen med de angivna laddningsalternativen.

### Exempel på källkod för LoadOptions med funktionen "Use Temp Folder" med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurera laddningsalternativ med funktionen "Använd temporär mapp".
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };

// Ladda dokumentet med en angiven tillfällig mapp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## Slutsats

den här guiden förklarade vi hur man laddar upp ett dokument med en viss temporär mapp med Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Genom att använda en temporär mapp kan temporära filer som genereras under dokumentbehandlingen lagras på ett organiserat och effektivt sätt.
