---
title: Minska PDF-filstorleken genom att inte bädda in kärnteckensnitt
linktitle: Minska PDF-filstorleken genom att inte bädda in kärnteckensnitt
second_title: Aspose.Words Document Processing API
description: Lär dig hur du minskar PDF-filstorleken genom att inte bädda in kärnteckensnitt när du konverterar Word-dokument till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

den här handledningen går vi igenom stegen för hur du minskar PDF-filstorleken genom att inte bädda in kärnteckensnitt med Aspose.Words för .NET. Den här funktionen låter dig styra om grundläggande typsnitt som Arial, Times New Roman, etc. måste bäddas in i PDF:en när du konverterar ett Word-dokument. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp Word-dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt Word-dokument.

## Steg 2: Ställ in PDF-konverteringsalternativ

Skapa en instans av klassen PdfSaveOptions och aktivera grundläggande teckensnittsinbäddning:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Det här alternativet styr om basteckensnitt ska bäddas in i PDF:en eller inte.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera Word-dokumentet till PDF genom att ange konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för Undvik att bädda in kärnteckensnitt med Aspose.Words för .NET

Här är den fullständiga källkoden för att använda funktionen för att undvika inbäddning av kärnteckensnitt med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Utdata-PDF-filen kommer inte att bäddas in med kärnteckensnitt som Arial, Times New Roman etc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Genom att följa dessa steg kan du enkelt kontrollera om basteckensnitt ska bäddas in i PDF:en när du konverterar ett Word-dokument med Aspose.Words för .NET.


## Slutsats

den här handledningen förklarade vi hur man minskar storleken på en PDF-fil genom att inte bädda in grundläggande typsnitt med Aspose.Words för .NET. Den här funktionen låter dig styra om basteckensnitt ska bäddas in i PDF:en när du konverterar ett Word-dokument. Genom att följa stegen som beskrivs kan du enkelt styra inbäddning eller icke-inbäddning av grundläggande typsnitt, vilket kan hjälpa till att minska PDF-filstorleken och säkerställa bättre kompatibilitet och ett konsekvent utseende av dokumentet på olika enheter och plattformar. Glöm inte att överväga konsekvenserna av att inte bädda in bastypsnitt och att experimentera för att säkerställa att dokumentet återges som förväntat.

### Vanliga frågor

#### F: Vad är alternativet att inte bädda in bastypsnitt i en PDF-fil och varför är det viktigt?
S: Alternativet att inte bädda in basteckensnitt i en PDF-fil styr om basteckensnitt som Arial, Times New Roman, etc. måste bäddas in i PDF:en när ett Word-dokument konverteras. Detta kan vara viktigt för att minska storleken på PDF-filen genom att undvika att inkludera typsnitt som är allmänt tillgängliga på PDF-läsarsystem. Det kan också hjälpa till att säkerställa bättre kompatibilitet och konsekvent utseende för PDF-dokumentet på olika enheter och plattformar.

#### F: Hur kan jag konfigurera Aspose.Words för .NET att inte bädda in basteckensnitt i en PDF-fil?
S: För att konfigurera Aspose.Words för .NET att inte bädda in kärnteckensnitt i en PDF-fil, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda Word-dokumentet du vill konvertera till PDF med hjälp av`Document` klass och den angivna dokumentsökvägen.

 Skapa en instans av`PdfSaveOptions`klass och ställ in`UseCoreFonts` egendom till`true`. Detta kommer att undvika inbäddning av bastypsnitt i den genererade PDF-filen.

 Använd`Save` metod för`Document` objekt för att spara dokumentet i PDF-format med angivande av konverteringsalternativen som konfigurerats tidigare.

#### F: Vilka är fördelarna med att inte bädda in bastypsnitt i en PDF-fil?
S: Fördelarna med att inte bädda in bastypsnitt i en PDF-fil är:

Reduktion av PDF-filstorlek: Genom att undvika att bädda in vanliga typsnitt som Arial, Times New Roman, etc., kan PDF-filstorleken minskas, vilket gör det lättare att lagra, dela och överföra filer.

Bättre kompatibilitet: Genom att använda grundläggande typsnitt som är allmänt tillgängliga på PDF-läsarsystem säkerställer du bättre kompatibilitet och dokumentutseende på olika enheter och plattformar.

#### F: Vilka är konsekvenserna av att inte bädda in bastypsnitt i en PDF-fil?
S: Konsekvenserna av att inte bädda in basteckensnitt i en PDF-fil är följande:

Annat utseende: Om basteckensnitten inte är tillgängliga i systemet där PDF:en öppnas kommer ersättningsteckensnitt att användas, vilket kan resultera i ett annat utseende än tänkt.

Läsbarhetsproblem: Ersättningsteckensnitt som används kanske inte är lika läsbara som de ursprungliga typsnitten, vilket kan påverka dokumentets läsbarhet.