---
title: Ändra stil på Toc-nivå
linktitle: Ändra stil på Toc-nivå
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du enkelt ändrar stilen på en innehållsförteckningsnivå i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och manipulera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words är möjligheten att ändra stilen på en viss nivå i ett dokuments innehållsförteckning. I den här guiden kommer vi att visa dig hur du använder C#-källkoden för Aspose.Words för .NET för att ändra stilen på en nivå i innehållsförteckningen i ett Word-dokument.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör arbetet med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, redigera och manipulera Word-dokument, inklusive att ändra stilen på innehållsförteckningen.

## Skapa ett nytt dokument

Det första steget är att skapa ett nytt Word-dokument där du vill ändra stilen för innehållsförteckningen. Använd klassen Document för att skapa ett nytt dokument. Här är ett exempel :

```csharp
Document doc = new Document();
```

det här exemplet skapar vi ett nytt tomt dokument.

## Ändra stilen på en innehållsförteckningsnivå

När dokumentet har skapats kan du komma åt dokumentstilar och ändra stilen som används för en specifik nivå i innehållsförteckningen. I det här exemplet kommer vi att ändra stilen som används för den första nivån i innehållsförteckningen. Här är hur:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

I det här exemplet använder vi egenskapen Styles för klassen Document för att komma åt dokumentstilar. Därefter använder vi stilidentifieraren StyleIdentifier.Toc1 för att komma åt stilen som används för den första nivån i innehållsförteckningen. Slutligen ändrar vi egenskapen Font.Bold för stilen för att göra den fet.

## Spara ändrat dokument

När du har gjort de nödvändiga ändringarna av stilen på innehållsförteckningen kan du spara det ändrade dokumentet med hjälp av Spara-metoden för klassen Dokument. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

I det här exemplet sparar vi det ändrade dokumentet som "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## Exempel på källkod för funktionen "Ändra stilen på en innehållsförteckningsnivå" med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa ett nytt dokument
Document doc = new Document();

// Ändring av stilen på den första nivån i innehållsförteckningen
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Spara det ändrade dokumentet
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Slutsats

I den här guiden förklarade vi hur man använder Aspose.Words för .NET för att ändra stilen på en nivå i innehållsförteckningen i ett Word-dokument med hjälp av den medföljande C#-källkoden. Genom att följa de angivna stegen kan du enkelt anpassa stilen på innehållsförteckningen i dina Word-dokument i ditt C#-program. Aspose.Words erbjuder enorm flexibilitet och kraft att arbeta med stilarna och formateringen av dina dokument, vilket gör att du kan skapa attraktiva och professionella Word-dokument.