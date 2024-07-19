---
title: Hämta Jpeg-sidintervall
linktitle: Hämta Jpeg-sidintervall
second_title: Aspose.Words Document Processing API
description: Lär dig hur du får en rad JPEG-sidor med Aspose.Words för .NET. Komplett handledning för att extrahera anpassade bilder.
type: docs
weight: 10
url: /sv/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

I den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för funktionen "Hämta utbud av JPEG-sidor" med Aspose.Words för .NET. Med den här funktionen kan du konvertera ett visst antal sidor i ett dokument till bilder i JPEG-format.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 I det här steget konfigurerar vi säkerhetskopieringsalternativ för bilder. Vi skapar en ny`ImageSaveOptions` objekt som anger önskat sparaformat, här "Jpeg" för JPEG-formatet. Vi ställer också in antalet sidor som ska konverteras med hjälp av`PageSet`objekt. Slutligen justerar vi bildens ljusstyrka och kontrast med hjälp av`ImageBrightness`och`ImageContrast` respektive fastigheter. Vi ändrar också den horisontella upplösningen med hjälp av`HorizontalResolution` fast egendom.

## Steg 4: Säkerhetskopiera bilder

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 I det här sista steget sparar vi bilderna för det angivna sidintervallet i JPEG-formatet med hjälp av`Save` metod och skicka sökvägen till utdatafilen, tillsammans med de angivna sparaalternativen.

Nu kan du köra källkoden för att konvertera ett visst antal sidor i ditt dokument till JPEG-bilder. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Exempel på källkod för Get Jpeg Page Range med Aspose.Words för .NET

```csharp 
 // Sökväg till din dokumentkatalog
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Ställ in "Siduppsättning" till "0" för att endast konvertera den första sidan i ett dokument.
options.PageSet = new PageSet(0);

// Ändra bildens ljusstyrka och kontrast.
// Båda är på en 0-1 skala och är på 0,5 som standard.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Ändra den horisontella upplösningen.
// Standardvärdet för dessa egenskaper är 96,0, för en upplösning på 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Slutsats

I den här handledningen utforskade vi funktionaliteten för att få ett JPEG-sidintervall med Aspose.Words för .NET. Vi lärde oss hur man konverterar ett visst antal sidor i ett dokument till bilder i JPEG-format, samtidigt som vi anpassar sparalternativen.

Den här funktionen är användbar när du vill extrahera specifika sidor från ett dokument och spara dem som JPEG-bilder. Du kan också justera bildernas ljusstyrka, kontrast och horisontella upplösning för att uppnå personliga resultat.

Aspose.Words för .NET erbjuder ett omfattande utbud av avancerade funktioner för dokumenthantering och generering. Att få ett JPEG-sidintervall är ett av de många kraftfulla verktyg det ställer till ditt förfogande.

Integrera gärna den här funktionen i dina Aspose.Words för .NET-projekt för att få högkvalitativa JPEG-bilder från dina dokument.