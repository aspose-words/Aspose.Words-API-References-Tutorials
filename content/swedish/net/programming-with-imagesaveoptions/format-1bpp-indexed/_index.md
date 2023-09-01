---
title: Format 1Bpp Indexerad
linktitle: Format 1Bpp Indexerad
second_title: Aspose.Words Document Processing API
description: Lär dig hur du formaterar bilder i 1 bpp indexerade med Aspose.Words för .NET. Komplett handledning för bilder med lågt färgdjup.
type: docs
weight: 10
url: /sv/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
I den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för funktionen "Format 1Bpp Indexed" med Aspose.Words för .NET. Den här funktionen låter dig formatera bilder i ett dokument i PNG-format med ett färgdjup på 1 bit per pixel (1 bpp) och ett indexerat färgläge.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 I det här steget konfigurerar vi säkerhetskopieringsalternativ för bilder. Vi skapar en ny`ImageSaveOptions`objekt som anger önskat sparaformat, här "Png" för PNG-formatet. Vi definierar också sidan som ska inkluderas i bilden, det svartvita färgläget och det indexerade pixelformatet på 1 bpp.

## Steg 4: Säkerhetskopiera bilder

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 I detta sista steg sparar vi dokumentbilderna i PNG-format med hjälp av`Save` metod och skicka sökvägen till utdatafilen, tillsammans med de angivna sparaalternativen.

Nu kan du köra källkoden för att formatera dokumentbilderna i PNG-format med ett färgdjup på 1 bpp indexerat. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Exempel på källkod för Format 1Bpp Indexerad med Aspose.Words för .NET

```csharp 
 
			 // Sökväg till din dokumentkatalog
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Slutsats

I den här handledningen utforskade vi funktionen 1Bpp Indexed format med Aspose.Words för .NET. Vi lärde oss hur man formaterar bilder i ett dokument i PNG-format med ett färgdjup på 1 bit per pixel (1 bpp) och ett indexerat färgläge.

Den här funktionen är användbar när du vill få bilder med lågt färgdjup och liten filstorlek. 1Bpp Indexed-formatet gör att bilder kan representeras med en indexerad färgpalett, vilket kan vara fördelaktigt för vissa specifika tillämpningar.

Aspose.Words för .NET erbjuder ett brett utbud av avancerade funktioner för dokumenthantering och generering. 1Bpp Indexed-formatet är ett av de många kraftfulla verktyg det ställer till ditt förfogande.