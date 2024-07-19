---
title: Dela Word-dokument efter sida
linktitle: Dela Word-dokument efter sida
second_title: Aspose.Words Document Processing API
description: Lär dig hur du delar upp ett Word-dokument i enskilda sidor med Aspose.Words för .NET. Detta kraftfulla API förenklar processen att dela upp dokument, vilket gör det effektivt och bekvämt.
type: docs
weight: 10
url: /sv/net/split-document/page-by-page/
---

I den här handledningen går vi igenom hur du delar upp ett Word-dokument i enskilda sidor med hjälp av dokumentbehandlingsfunktionen i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och få separata dokument för varje sida.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för ditt dokument och ladda dokumentet i ett dokumentobjekt. Här är hur:

```csharp
//Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Steg 2: Dokumentdelning per sida

Nu går vi igenom varje sida i dokumentet och delar upp dokumentet i enskilda sidor. Här är hur:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Spara varje sida som ett separat dokument.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Exempel på källkod för sida för sida med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Sida för sida i Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Spara varje sida som ett separat dokument.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Med denna kod kommer du att kunna dela upp ett Word-dokument i enskilda sidor med Aspose.Words för .NET. Du kan även slå samman separata dokument om det behövs.

## Slutsats

Grattis! Du har lärt dig hur du delar upp ett Word-dokument i enskilda sidor med hjälp av funktionen Sida för sida i Aspose.Words för .NET. Genom att följa den medföljande källkoden kan du extrahera varje sida i ett dokument och spara dem som separata dokument.

Att dela upp ett dokument efter sida kan vara användbart när du behöver arbeta med specifika sidor eller distribuera innehåll på ett detaljerat sätt. Aspose.Words för .NET tillhandahåller ett kraftfullt API som förenklar processen att dela upp dokument, vilket gör det effektivt och bekvämt.

Utforska gärna andra funktioner som erbjuds av Aspose.Words för .NET för att förbättra dina dokumentbehandlingsmöjligheter och effektivisera ditt arbetsflöde.

### Vanliga frågor

#### Hur kan jag dela upp ett dokument på flera sidor med Aspose.Words för .NET?

 För att dela upp ett dokument på flera sidor kan du använda`ExtractPages` metod för Aspose.Words API för att få sidintervall. Genom att ange startsidan och antalet sidor som ska extraheras kan du skapa separata dokument för varje sida.

#### Kan jag anpassa utdataformatet när jag delar upp ett dokument efter sida?

Ja, Aspose.Words för .NET stöder olika utdataformat när du delar upp ett dokument efter sida. Du kan spara varje sida som ett separat dokument i format som DOCX, PDF, HTML och mer, beroende på dina krav.

#### Kan jag dela upp ett dokument efter ett specifikt sidintervall?

Absolut! Aspose.Words för .NET låter dig dela upp ett dokument efter ett specifikt sidintervall. Genom att justera startsidan och antalet sidor som ska extraheras kan du exakt definiera sidintervallet för att dela upp dokumentet.

#### Är det möjligt att slå samman de delade dokumenten till ett enda dokument?

Ja, du kan slå ihop de delade dokumenten tillbaka till ett enda dokument med hjälp av sammanslagningsfunktionen som tillhandahålls av Aspose.Words för .NET. Genom att kombinera de separata dokumenten kan du återskapa originaldokumentet eller skapa ett nytt dokument med en annan struktur, efter behov.