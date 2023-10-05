---
title: Exponera tröskelkontroll för Tiff-binarisering
linktitle: Exponera tröskelkontroll för Tiff-binarisering
second_title: Aspose.Words Document Processing API
description: Lär dig hur du kontrollerar TIFF-binariseringströskeln med Aspose.Words för .NET. Komplett handledning för bättre bilder.
type: docs
weight: 10
url: /sv/net/programming-with-imagesaveoptions/expose-threshold-control-for-tiff-binarization/
---
I den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för funktionen "TIFF Binarization Threshold Control Exposure" med Aspose.Words för .NET. Denna funktion låter dig styra binariseringströskeln när du konverterar ett dokument till TIFF-format.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Ladda dokumentet

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 I det här steget laddar vi dokumentet med hjälp av`Document` metod och skickar sökvägen till DOCX-filen som ska laddas.

## Steg 3: Konfigurera alternativ för säkerhetskopiering av bilder

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
TiffCompression = TiffCompression.Ccitt3,
ImageColorMode = ImageColorMode.Grayscale,
TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
ThresholdForFloydSteinbergDithering = 254
};
```

 I det här steget konfigurerar vi säkerhetskopieringsalternativ för bilder. Vi skapar en ny`ImageSaveOptions` objekt som anger önskat sparaformat, här "Tiff" för TIFF-formatet. Vi ställer också in komprimeringsalternativ, bildfärgsläge och TIFF-binariseringsmetod med specificerad binariseringströskel.

## Steg 4: Säkerhetskopiera bilder

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
```

 I det här sista steget sparar vi dokumentbilderna i TIFF-format med hjälp av`Save` metod och skicka sökvägen till utdatafilen, tillsammans med de angivna sparaalternativen.

Nu kan du köra källkoden för att konvertera ditt dokument till TIFF-format samtidigt som du kontrollerar binariseringströskeln med de angivna alternativen. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff".

### Exempel på källkod Exponeringströskelkontroll för Tiff-binarisering

```csharp 

// Sökväg till din dokumentkatalog
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	TiffCompression = TiffCompression.Ccitt3,
	ImageColorMode = ImageColorMode.Grayscale,
	TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
	ThresholdForFloydSteinbergDithering = 254
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
            
        
```

### Slutsats

I den här handledningen utforskade vi exponeringsfunktionen i TIFF Binarization Threshold Control med Aspose.Words för .NET. Vi lärde oss hur man kontrollerar binariseringströskeln när man konverterar ett dokument till TIFF-format.

Den här funktionen är användbar när du vill justera binariseringströskeln för att få TIFF-bilder med bättre kvalitet och klarhet. Genom att ange binariseringströskeln med sparalternativ kan du få anpassade resultat skräddarsydda efter dina behov.

Aspose.Words för .NET erbjuder ett brett utbud av avancerade funktioner för dokumenthantering och generering. Att exponera TIFF-binariseringströskelkontrollen är ett av de många kraftfulla verktyg den ställer till ditt förfogande.

Inkludera gärna den här funktionen i dina Aspose.Words for .NET-projekt för att uppnå TIFF-bilder av hög kvalitet med exakt binariseringströskelkontroll.