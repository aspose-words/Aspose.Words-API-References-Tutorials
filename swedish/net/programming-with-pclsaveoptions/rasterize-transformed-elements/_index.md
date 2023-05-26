---
title: Rasterisera transformerade element
linktitle: Rasterisera transformerade element
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du inaktiverar rastrering av transformerade element när du konverterar till PCL-format med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, manipulera och konvertera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words är möjligheten att rastrera transformerade element när du konverterar dokument till olika format. I den här guiden kommer vi att visa dig hur du använder C#-källkoden för Aspose.Words för .NET för att inaktivera rastrering av transformerade element när du konverterar ett dokument till PCL-format.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör arbetet med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, redigera och konvertera Word-dokument, inklusive stöd för rastrering av transformerade element under konvertering.

## Laddar Word-dokumentet

Det första steget är att ladda Word-dokumentet du vill konvertera till PCL-format. Använd klassen Document för att ladda dokumentet från källfilen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

det här exemplet laddar vi "Rendering.docx"-dokumentet som finns i dokumentkatalogen.

## Konfigurera alternativ för säkerhetskopiering

Nästa steg är att konfigurera sparalternativen för konvertering till PCL-format. Använd klassen PclSaveOptions och ställ in egenskapen RasterizeTransformedElements till false. Så här gör du:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Vi skapar ett nytt PclSaveOptions-objekt och ställer in egenskapen SaveFormat till SaveFormat.Pcl för att ange att vi vill spara dokumentet i PCL-format. Därefter satte vi egenskapen RasterizeTransformedElements till false för att inaktivera rasterisering av transformerade element.

## Konvertera dokumentet till PCL-format

Nu när vi har konfigurerat sparalternativen kan vi fortsätta att konvertera dokumentet till PCL-format. Använd metoden Spara för klassen Document för att spara det konverterade dokumentet i PCL-format genom att ange sparalternativ. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

I det här exemplet sparar vi det konverterade dokumentet som "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" med de angivna sparalternativen.

### Exempel på källkod för "Rasterize Transformed Elements"-funktionen med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Ladda Word-dokumentet


Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurera alternativ för backup för konvertering till PCL-format
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Konvertera dokumentet till PCL-format
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Slutsats

I den här guiden tog vi upp hur man använder Aspose.Words för .NET för att inaktivera rastrering av transformerade element när man konverterar ett dokument till PCL-format med den medföljande C#-källkoden. Genom att följa de angivna stegen kan du enkelt kontrollera rastreringsbeteendet för transformerade element när du konverterar dina Word-dokument till olika format. Aspose.Words erbjuder en enorm flexibilitet och kraft att arbeta med de transformerade elementen, så att du kan skapa konverterade dokument exakt efter dina specifika behov.