---
title: Minska PDF-storleken genom att inaktivera inbäddade teckensnitt
linktitle: Minska PDF-storleken genom att inaktivera inbäddade teckensnitt
second_title: Aspose.Words Document Processing API
description: Lär dig hur du minskar PDF-storleken genom att inaktivera Windows-fontinbäddning när du konverterar dokument till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

I den här handledningen går vi igenom stegen för att minska PDF-storleken genom att inaktivera Windows-fontinbäddning i ett PDF-dokument med Aspose.Words för .NET. Genom att inaktivera teckensnittsinbäddning kan du minska storleken på den genererade PDF-filen. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Ställ in PDF-sparalternativ

Skapa en instans av klassen PdfSaveOptions och ange hur teckensnitt ska bäddas in:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Det här alternativet låter dig inaktivera integrationen av Windows-teckensnitt i den genererade PDF-filen.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för Inaktivera bädda in Windows-teckensnitt med Aspose.Words för .NET

Här är den fullständiga källkoden för att inaktivera inbäddning av Windows-teckensnitt i ett PDF-dokument med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Utdata-PDF-filen kommer att sparas utan att bädda in vanliga Windows-teckensnitt.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Genom att följa dessa steg kan du enkelt inaktivera inbäddningen av Windows-teckensnitt i ett PDF-dokument med Aspose.Words för .NET.


## Slutsats

den här handledningen lärde vi oss hur man minskar storleken på en PDF-fil genom att inaktivera inbäddning av Windows-teckensnitt med Aspose.Words för .NET. Genom att inaktivera teckensnittsinbäddning kan du minska storleken på den genererade PDF-filen, vilket gör det lättare att lagra, dela och överföra filer. Det är dock viktigt att notera att om du inaktiverar Windows-teckensnittsinbäddning kan det leda till ändringar av utseende och formatering i det slutliga PDF-dokumentet. Var noga med att överväga dessa konsekvenser när du använder den här funktionen. Utforska gärna fler funktioner i Aspose.Words för .NET för att optimera genereringen av dina PDF-filer.

### Vanliga frågor

#### F: Vad är att inaktivera Windows-fontinbäddning i ett PDF-dokument och varför är det viktigt?
S: Att inaktivera inbäddning av Windows-teckensnitt i ett PDF-dokument är processen för att förhindra att Windows-teckensnitt inkluderas i den genererade PDF-filen. Detta minskar storleken på PDF-filen genom att ta bort inbäddade Windows-teckensnittsdata. Detta kan vara viktigt för att minska storleken på PDF-filer, vilket kan göra dem lättare att lagra, dela och överföra snabbare.

#### F: Hur kan jag inaktivera Windows-fontinbäddning i ett PDF-dokument med Aspose.Words för .NET?
S: För att inaktivera inbäddning av Windows-teckensnitt i ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Ladda dokumentet du vill konvertera till PDF med hjälp av`Document` klass och dokumentsökväg.

 Skapa en instans av`PdfSaveOptions` klass och ställ in`FontEmbeddingMode`egendom till`PdfFontEmbeddingMode.EmbedNone`. Detta inaktiverar inbäddningen av Windows-teckensnitt i den genererade PDF-filen.

 Använd`Save` metod för`Document` objekt för att konvertera dokumentet till PDF med angivande av konverteringsalternativen som konfigurerats tidigare.

#### F: Vilka är fördelarna med att inaktivera Windows-fontinbäddning i ett PDF-dokument?
S: Fördelarna med att inaktivera Windows-fontinbäddning i ett PDF-dokument är:

Minskad PDF-filstorlek: Genom att inaktivera Windows-teckensnittsinbäddning tas inbäddade Windows-teckensnittsdata bort, vilket minskar storleken på den genererade PDF-filen.

Enklare lagring: Mindre PDF-filer är lättare att lagra, spara och överföra.

Snabbare delning och överföring: Mindre PDF-filer kan delas och överföras snabbare, vilket sparar tid och resurser.

#### F: Vilka är konsekvenserna av att inaktivera Windows-fontinbäddning i ett PDF-dokument?
S: Att inaktivera inbäddningen av Windows-teckensnitt i ett PDF-dokument kan leda till konsekvenser som:

Förlust av utseende och formatering: Om de Windows-teckensnitt som anges i dokumentet inte är tillgängliga på systemet där PDF-filen öppnas kommer ersättningsteckensnitt att användas, vilket kan resultera i ett felaktigt utseende och formatering. annorlunda till formen än de förväntade.

Läsbarhetsproblem: Om de ersättningsteckensnitt som används inte är lika läsbara som de ursprungliga typsnitten kan det påverka läsbarheten för texten i PDF-dokumentet.