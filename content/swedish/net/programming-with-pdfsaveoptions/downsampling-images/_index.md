---
title: Minska PDF-dokumentstorleken med nedsampling av bilder
linktitle: Minska PDF-dokumentstorleken med nedsampling av bilder
second_title: Aspose.Words Document Processing API
description: Lär dig hur du minskar pdf-dokumentstorleken med nedsampling av bilder när du konverterar till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/downsampling-images/
---

I den här handledningen går vi igenom stegen för att minska pdf-dokumentstorleken med nedsampling av bilder när du konverterar till PDF med Aspose.Words för .NET. Detta minskar storleken på den genererade PDF-filen. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Konfigurera PDF-sparalternativ

Skapa en instans av klassen PdfSaveOptions och ställ in alternativen för nedskalning av bilden:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 De`Resolution` egenskapen anger målupplösningen för bilderna och`ResolutionThreshold`egenskapen anger den lägsta upplösningen under vilken bilderna inte kommer att skalas ned.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av sparalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för nedsampling av bilder med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Vi kan ställa in en lägsta tröskel för nedsampling.
	// Detta värde förhindrar att den andra bilden i inmatningsdokumentet nedsamplas.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Genom att följa dessa steg kan du enkelt minska bildupplösningen när du konverterar till PDF med Aspose.Words för .NET.

## Slutsats

den här handledningen har vi förklarat hur man minskar storleken på ett PDF-dokument med bildsampling när man konverterar till PDF med Aspose.Words för .NET. Genom att följa stegen som beskrivs kan du enkelt minska upplösningen på bilder och storleken på den genererade PDF-filen. Var noga med att ange rätt sökväg till ditt dokument och konfigurera bildsamplingsalternativen efter behov. Att minska storleken på PDF-filen gör det lättare att dela, lagra och snabbt ladda filen på olika plattformar. Njut av fördelarna med att minska PDF-dokumentstorleken med bildsampling med Aspose.Words för .NET.

### Vanliga frågor

#### F: Vad är att minska storleken på PDF-dokumentet med bildsampling?
S: Att minska PDF-dokumentstorleken med bildsampling är att minska storleken på den genererade PDF-filen genom att minska upplösningen på bilderna vid konvertering till PDF. Detta optimerar användningen av lagringsutrymme och gör det lättare att dela och överföra PDF-filen.

#### F: Hur kan jag minska PDF-dokumentets storlek med bildsampling med Aspose.Words för .NET?
S: För att minska PDF-dokumentets storlek med bildsampling med Aspose.Words för .NET, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda dokumentet du vill konvertera till PDF med hjälp av`Document` klass och ange sökvägen till dokumentet i den angivna dokumentkatalogen.

 Konfigurera spara som PDF-alternativ genom att skapa en instans av`PdfSaveOptions` klass och ställ in bildsamplingsalternativen med hjälp av`DownsampleOptions` fast egendom. Du kan ange målupplösningen för bilder med hjälp av`Resolution` egenskapen och ställ in en lägsta upplösningströskel över vilken bilder inte kommer att skalas ned med hjälp av`ResolutionThreshold` fast egendom.

 Spara dokumentet i PDF-format med hjälp av`Save` metod för`Document` klass som anger sökvägen och sparalternativ.

#### F: Vilka är fördelarna med att minska PDF-dokumentstorleken med bildsampling?
S: Fördelarna med att minska PDF-dokumentstorleken med bildsampling är:

Minskad PDF-filstorlek: Bildsampling minskar upplösningen av bilder i PDF-dokumentet, vilket resulterar i en betydande minskning av PDF-filstorleken. Detta gör det enkelt att dela och överföra filen, särskilt via e-post eller online.

Optimering av lagringsutrymme: Att minska storleken på PDF-filen hjälper till att optimera användningen av lagringsutrymme, särskilt när du har många PDF-filer som innehåller högupplösta bilder.

Prestandaförbättringar: Mindre PDF-filer laddas snabbare och kan öppnas och visas snabbare på olika enheter.