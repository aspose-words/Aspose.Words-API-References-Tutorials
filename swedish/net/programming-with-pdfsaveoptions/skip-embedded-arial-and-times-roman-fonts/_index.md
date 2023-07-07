---
title: Optimera PDF-storlek med Skip Embedded Arial och Times Roman-teckensnitt
linktitle: Optimera PDF-storlek med Skip Embedded Arial och Times Roman-teckensnitt
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att generera optimerad PDF utan att bädda in Arial- och Times Roman-teckensnitt med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för att optimera PDF-storlek genom att hoppa över inbäddade Arial- och Times Roman-teckensnitt till metafilstorlek med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du konfigurerar alternativet för typsnittsinbäddningsläge i ett dokument och genererar en PDF utan att bädda in Arial- och Times Roman-teckensnitt.

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

## Steg 3: Konfigurera spara som PDF-alternativ med teckensnittsinbäddning

 För att hoppa över att bädda in Arial- och Times Roman-teckensnitt i den genererade PDF-filen måste vi konfigurera`PdfSaveOptions` objekt och ställ in`FontEmbeddingMode` egendom till`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Steg 4: Spara dokumentet som PDF utan inbäddade teckensnitt

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt skapat en PDF utan att bädda in Arial- och Times Roman-teckensnitt med Aspose.Words för .NET.

### Exempel på källkod för att hoppa över inbäddade Arial- och Times Roman-teckensnitt i metafilstorlek med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Slutsats

den här handledningen förklarade vi hur man inaktiverar inbäddningen av Arial- och Times Roman-teckensnitt i ett PDF-dokument med Aspose.Words för .NET. Genom att följa stegen som beskrivs kan du skapa en PDF-fil utan att bädda in dessa specifika teckensnitt, vilket kan hjälpa till att minska filstorleken och säkerställa bättre dokumentkompatibilitet över olika plattformar. Var noga med att överväga konsekvenserna av att inaktivera teckensnittsinbäddning när du använder den här funktionen. Utforska gärna fler funktioner i Aspose.Words för .NET för att optimera genereringen av dina PDF-filer.

### Vanliga frågor

#### F: Vad är det som inaktiverar inbäddning av Arial- och Times Roman-teckensnitt i ett PDF-dokument och varför är det viktigt?
S: Att inaktivera inbäddningen av Arial- och Times Roman-teckensnitt i ett PDF-dokument är processen att inte inkludera dessa teckensnitt i den genererade PDF-filen. Detta kan vara viktigt för att minska storleken på PDF-filen genom att undvika att inkludera teckensnitt som redan är allmänt tillgängliga på PDF-läsarsystem. Det kan också hjälpa till att säkerställa bättre kompatibilitet och konsekvent utseende för PDF-dokumentet på olika enheter och plattformar.

#### F: Hur kan jag konfigurera Aspose.Words för .NET att inte bädda in Arial- och Times Roman-teckensnitt i ett PDF-dokument?
S: För att konfigurera Aspose.Words för .NET att inte bädda in Arial- och Times Roman-teckensnitt i ett PDF-dokument, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda dokumentet du vill bearbeta med hjälp av`Document` klass och den angivna dokumentsökvägen.

 Skapa en instans av`PdfSaveOptions` klass och ställ in`FontEmbeddingMode` egendom till`PdfFontEmbeddingMode.EmbedAll`. Detta kommer att bädda in alla typsnitt utom Arial och Times Roman i den genererade PDF-filen.

 Använd`Save` metod för`Document` objekt för att spara dokumentet i PDF-format med angivande av sparade alternativ som konfigurerats tidigare.

#### F: Vilka är fördelarna med att inaktivera Arial- och Times Roman-teckensnittsinbäddning i ett PDF-dokument?
S: Fördelarna med att inaktivera Arial- och Times Roman-teckensnittsinbäddning i ett PDF-dokument är:

Reducering av PDF-filstorlek: Genom att undvika att bädda in vanliga typsnitt som Arial och Times Roman kan PDF-filstorleken minskas, vilket gör det lättare att lagra, dela och överföra filer.

Bättre kompatibilitet: Genom att använda typsnitt som är allmänt tillgängliga på PDF-läsarsystem säkerställer du bättre kompatibilitet och utseende av dokumentet på olika enheter och plattformar.

#### F: Vilka är konsekvenserna av att inaktivera inbäddningen av Arial- och Times Roman-teckensnitt i ett PDF-dokument?
S: Konsekvenserna av att inaktivera inbäddningen av Arial- och Times Roman-teckensnitt i ett PDF-dokument är följande:

Annat utseende: Om Arial- och Times Roman-teckensnitt inte är tillgängliga på systemet där PDF-filen öppnas, kommer ersättningsteckensnitt att användas, vilket kan resultera i ett annat utseende än avsett.

Läsbarhetsproblem: Ersättningsteckensnitt som används kanske inte är lika läsbara som teckensnitten i ursprunget, vilket kan påverka dokumentets läsbarhet.