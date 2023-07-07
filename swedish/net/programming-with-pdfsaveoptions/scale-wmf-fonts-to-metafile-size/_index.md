---
title: Minska PDF-storleken med skala Wmf-teckensnitt till metafilstorlek
linktitle: Minska PDF-storleken med skala Wmf-teckensnitt till metafilstorlek
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg guide för att minska pdf-storlek med skala wmf-teckensnitt till metafilstorlek vid konvertering till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Den här artikeln ger en steg-för-steg-guide om hur man minskar pdf-storlek med skala wmf-teckensnitt till metafilstorlek med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du aktiverar eller inaktiverar WMF-teckensnittsskalning när du konverterar till PDF.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "WMF med text.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Steg 3: Konfigurera alternativ för metafilrendering

 För att aktivera eller inaktivera WMF-teckensnittsskalning till metafilstorlek måste vi konfigurera`MetafileRenderingOptions`objekt. I det här exemplet inaktiverar vi teckensnittsskalning genom att ställa in`ScaleWmfFontsToMetafileSize` egendom till`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Steg 4: Konfigurera spara som PDF-alternativ med alternativ för metafilrendering

Slutligen kan vi konfigurera spara-till-PDF-alternativen med hjälp av metafilåtergivningsalternativen som konfigurerats tidigare.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Steg 5: Spara dokument som PDF med metafilåtergivningsalternativ

Spara dokumentet i PDF-format med de tidigare konfigurerade sparalternativen.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt aktiverat eller inaktiverat WMF-teckensnittsskalning till metafilstorlek vid konvertering

ett PDF-dokument med Aspose.Words för .NET.

### Exempel på källkod för att skala WMF-teckensnitt till metafilstorlek med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Om Aspose.Words inte kan rendera några av metafilposterna korrekt till vektorgrafik
	// sedan renderar Aspose.Words denna metafil till en bitmapp.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Slutsats

den här handledningen förklarade vi hur man aktiverar eller inaktiverar storleksändring av WMF-teckensnitt till metafilstorlek i ett PDF-dokument med Aspose.Words för .NET. Genom att följa stegen som beskrivs kan du enkelt kontrollera om WMF-teckensnitt ska ändras för att matcha metafilstorleken vid konvertering till ett PDF-dokument. Detta kan hjälpa dig att minska storleken på den genererade PDF-filen och förbättra renderingsprestanda. Var noga med att ange rätt sökväg till dina dokument och konfigurera alternativen för metafilrendering efter behov.

### Vanliga frågor

#### F: Vad är att ändra storlek på WMF-teckensnitt till metafilstorlek i ett PDF-dokument?
S: Ändra storlek på WMF-teckensnitt till metafilstorlek i ett PDF-dokument är en funktion som styr om WMF-teckensnitt ska skalas för att matcha metafilstorleken vid konvertering till ett PDF-dokument. När den här funktionen är aktiverad skalas WMF-teckensnitt för att matcha storleken på metafilen, vilket kan minska storleken på det genererade PDF-dokumentet.

#### F: Hur kan jag använda Aspose.Words för .NET för att aktivera eller inaktivera storleksändring av WMF-teckensnitt till metafilstorlek i ett PDF-dokument?
S: För att aktivera eller inaktivera storleksändring av WMF-teckensnitt till metafilstorlek i ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda dokumentet du vill bearbeta med hjälp av`Document` klass och ange sökvägen till Word-dokumentet i den angivna dokumentkatalogen.

 Konfigurera alternativ för metafilrendering genom att skapa en instans av`MetafileRenderingOptions` klass och ställa in`ScaleWmfFontsToMetafileSize` egendom till`true` för att möjliggöra skalning av WMF-teckensnitt till metafilstorlek, eller till`false` för att inaktivera den här funktionen.

 Konfigurera alternativen för att spara som PDF genom att skapa en instans av`PdfSaveOptions` klass och använda alternativen för metafilrendering som konfigurerats tidigare.

 Spara dokumentet i PDF-format med hjälp av`Save` metod för`Document`klass som anger sökvägen och sparalternativ.

#### F: Vilka är fördelarna med att ändra storlek på WMF-teckensnitt till metafilstorlek i ett PDF-dokument?
S: Fördelarna med att ändra storlek på WMF-teckensnitt till metafilstorlek i ett PDF-dokument är:

Reduktion av PDF-filstorlek: Ändra storlek på WMF-teckensnitt till metafilstorlek kan minska storleken på det genererade PDF-dokumentet genom att anpassa teckensnittsstorleken till metafilbehoven.

Förbättrad prestanda: Genom att anpassa storleken på WMF-teckensnitt till metafilens mått kan renderingen av PDF-dokumentet bli snabbare och effektivare.