---
title: Bädda in delmängdsteckensnitt i PDF-dokument
linktitle: Bädda in delmängdsteckensnitt i PDF-dokument
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att bädda in teckensnittsundergrupper i ett PDF-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för inbäddning av teckensnittsdelmängder med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av den här handledningen kommer du att kunna förstå hur du bäddar in delmängder av teckensnitt i ett dokument och genererar en PDF som endast innehåller de glyfer som används i dokumentet.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "Rendering.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 3: Konfigurera spara som PDF-alternativ

 För att skapa en PDF-fil som endast innehåller de delmängder av teckensnitt som används i dokumentet måste vi konfigurera`PdfSaveOptions` objekt med`EmbedFullFonts` egenskapen inställd på`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Steg 4: Spara dokument som PDF med teckensnittsunderuppsättningar

 Slutligen kan vi spara dokumentet som en PDF med hjälp av teckensnittsunderuppsättningarna. Ange utdatafilens namn och`saveOptions` objekt som vi konfigurerade i föregående steg.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt bäddat in delmängder av teckensnitt i ett dokument och genererat en PDF som endast innehåller de glyfer som används i dokumentet med Aspose.Words för .NET.

### Exempel på källkod för att bädda in teckensnittsundergrupper med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Utdata-PDF-filen kommer att innehålla underuppsättningar av teckensnitten i dokumentet.
	// Endast de glyfer som används i dokumentet ingår i PDF-teckensnitten.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Slutsats

I den här handledningen lärde vi oss hur man bäddar in teckensnittsundergrupper i ett PDF-dokument med Aspose.Words för .NET. Att bädda in delmängder av teckensnitt hjälper till att minska storleken på PDF-filen samtidigt som dokumentets utseende bevaras genom att endast använda de tecken som faktiskt används. Detta säkerställer bättre kompatibilitet och prestanda vid visning och utskrift av PDF-filen. Utforska gärna funktionerna i Aspose.Words för .NET ytterligare för att optimera genereringen av dina PDF-dokument med inbäddade teckensnittsundergrupper.

### Vanliga frågor

#### F: Vad är att bädda in teckensnittsundergrupper i ett PDF-dokument?
S: Att bädda in teckensnittsunderuppsättningar i ett PDF-dokument är processen att bara inkludera de glyfer som används i dokumentet, snarare än att inkludera alla fullständiga teckensnitt. Detta minskar storleken på PDF-filen genom att endast inkludera de teckensnittsdata som behövs för att visa de tecken som faktiskt används i dokumentet.

#### F: Vad är skillnaden mellan att bädda in fullständiga teckensnitt och bädda in delmängder av teckensnitt?
S: Inbäddning av fullständigt teckensnitt innebär att alla teckensnitt som används i dokumentet inkluderas i PDF-filen, vilket säkerställer att dokumentet kommer att visas exakt som det designades, men kan öka storleken på PDF-filen. Däremot innehåller inbäddade teckensnittsunderuppsättningar endast de glyfer som används i dokumentet, vilket minskar storleken på PDF-filen, men begränsar möjligheten att exakt replikera dokumentets utseende om ytterligare tecken läggs till senare.

#### F: Hur kan jag bädda in teckensnittsundergrupper i ett PDF-dokument med Aspose.Words för .NET?
S: För att bädda in teckensnittsundergrupper i ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Ställ in sökvägen till dokumentkatalogen genom att ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda dokumentet du vill bearbeta med hjälp av`Document` klass och dokumentsökvägen.

 Konfigurera PDF-sparalternativ genom att skapa en instans av`PdfSaveOptions` klass och ställa in`EmbedFullFonts` egendom till`false`Detta säkerställer att endast de teckensnittsunderuppsättningar som används i dokumentet kommer att inkluderas i PDF-filen.

 Spara dokumentet i PDF-format med teckensnittsunderuppsättningarna inbäddade med hjälp av`Save` metod för`Document` objekt, ange namnet på utdatafilen och spara alternativen som konfigurerats tidigare.

#### F: Vilka är fördelarna med att bädda in teckensnittsundergrupper i ett PDF-dokument?
S: Fördelarna med att bädda in teckensnittsundergrupper i ett PDF-dokument är:

Minskad PDF-filstorlek: Genom att endast inkludera de glyfer som används i dokumentet, reduceras PDF-filstorleken jämfört med att bädda in fullständiga teckensnitt.

Bevarande av dokumentets utseende: Underuppsättningarna av teckensnitt som ingår i PDF-filen gör det möjligt att återskapa dokumentets utseende med endast de tecken som faktiskt används.

Kompatibilitet med licensens begränsningar: Inbäddning av underuppsättningar av teckensnitt kan föredras i fall där fullständiga teckensnitt inte kan bäddas in lagligt på grund av licensbegränsningar.