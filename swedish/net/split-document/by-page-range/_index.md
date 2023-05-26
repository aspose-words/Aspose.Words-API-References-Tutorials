---
title: Efter sidintervall
linktitle: Efter sidintervall
second_title: Aspose.Words för .NET API Referens
description: Extrahera enkelt efter sidintervall från ett Word-dokument med hjälp av Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/split-document/by-page-range/
---

## Introduktion
I den här handledningen guidar vi dig steg för steg för att förstå och använda funktionen "By Page Range" i Aspose.Words för .NET. Den här funktionen låter dig extrahera en specifik del av ett stort Word-dokument med ett visst sidintervall. Vi kommer att förse dig med komplett källkod och Markdown-utdataformat för att göra det lättare för dig att förstå och använda senare.

## Krav
Innan du börjar, se till att du har följande på plats:

1. Aspose.Words för .NET installerat på din utvecklingsmaskin.
2. En stor Word-fil som du vill extrahera en specifik del från.

Nu när vi har täckt kraven kan vi gå vidare till stegen för att använda funktionen Efter sidaintervall.

## Steg 1: Dokumentinitiering och laddning
När du har ställt in din utvecklingsmiljö måste du initiera och ladda Word-dokumentet från vilket du vill extrahera en specifik del. Här är koden att använda:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

Se till att ersätta "YOUR_DOCUMENTS_DIRECTORY" med den faktiska sökvägen till din dokumentkatalog och "Name_of_large_document.docx" med namnet på din stora Word-fil.

## Steg 2: Extrahera delen av dokumentet
 Nu när vi har laddat dokumentet kan vi extrahera den specifika delen med hjälp av`ExtractPages` funktion med önskat sidintervall. Så här gör du:

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

I det här exemplet extraherar vi sidorna 3-6 från originaldokumentet. Du kan justera sidnumren efter dina behov.

## Steg 3: Spara den extraherade delen
När vi har extraherat de önskade sidorna kan vi spara dem i ett nytt Word-dokument. Här är hur:

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

Se till att ersätta "Document_Extraits.ParPlageDePages.docx" med önskat namn för din utdatafil.

### Exempel på källkod för By Page Range med Aspose.Words för .NET

```csharp

            // Sökvägen till dokumentkatalogen.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(MyDir + "Big document.docx");
            
            // Hämta en del av dokumentet.
            Document extractedPages = doc.ExtractPages(3, 6);
            extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
            
        
```

## Slutsats
Grattis! Du har lärt dig hur du använder "By Page Range" från Aspose.Words för .NET. Nu kan du enkelt extrahera specifika delar av ett stort Word-dokument med ett visst sidintervall. Experimentera gärna mer med Asposes andra kraftfulla funktioner. .Ord för att möta dina specifika behov.

