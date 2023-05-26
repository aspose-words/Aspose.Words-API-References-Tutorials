---
title: Få Tiff Page Range
linktitle: Få Tiff Page Range
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du extraherar en rad TIFF-sidor med Aspose.Words för .NET. Komplett handledning för anpassade TIFF-filer.
type: docs
weight: 10
url: /sv/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

den här handledningen kommer vi att utforska den medföljande C#-källkoden för att få en rad TIFF-sidor med Aspose.Words för .NET. Med den här funktionen kan du extrahera ett specifikt intervall av sidor från ett dokument och spara dem som en TIFF-fil.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Ladda dokumentet

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 I det här steget laddar vi dokumentet med hjälp av`Document` metod och skickar sökvägen till DOCX-filen som ska laddas.

## Steg 3: Spara hela dokumentet i TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 I det här steget sparar vi hela dokumentet i TIFF-format med hjälp av`Save` metod och ange sökvägen till utdatafilen med tillägget`.tiff`.

## Steg 4: Konfigurera alternativ för säkerhetskopiering för sidintervallet

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 I det här steget konfigurerar vi säkerhetskopieringsalternativ för det specifika sidintervallet. Vi skapar en ny`ImageSaveOptions` objekt som anger önskat sparaformat, här "Tiff" för TIFF-formatet. Vi använder`PageSet` för att ange vilket antal sidor vi vill extrahera, här från sida 0 till sida 1 (inklusive). Vi ställer också in TIFF-komprimeringen till`Ccitt4` och upplösningen till 160 dpi.

## Steg 5: Spara sidintervallet till TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 I det här sista steget sparar vi det angivna sidintervallet i TIFF-format med hjälp av`Save`metod och skickar sökvägen till utdatafilen med`.tiff` tillägg, tillsammans med de angivna sparalternativen .

Nu kan du köra källkoden för att hämta ett visst antal sidor från ditt dokument och spara dem som en TIFF-fil. De resulterande filerna kommer att sparas i den angivna katalogen med namnen "WorkingWithImageSaveOptions.MultipageTiff.tiff" för hela dokumentet och "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" för det angivna sidintervallet.

### Exempel på källkod för Get Tiff Page Range med Aspose.Words för .NET

```csharp 

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Slutsats

I den här handledningen utforskade vi funktionaliteten för att få en rad TIFF-sidor med Aspose.Words för .NET. Vi lärde oss hur man extraherar ett specifikt intervall av sidor från ett dokument och sparar dem som en TIFF-fil.

Den här funktionen är användbar när du bara vill extrahera vissa sidor från ett dokument och spara dem i ett standardbildformat som TIFF. Du kan också anpassa komprimerings- och upplösningsalternativen för att få TIFF-filer av bästa kvalitet.

Aspose.Words för .NET erbjuder ett omfattande utbud av avancerade funktioner för dokumenthantering och generering. Att få ett TIFF-sidintervall är ett av de många kraftfulla verktyg det ställer till ditt förfogande.

Integrera den här funktionen i dina Aspose.Words för .NET-projekt för att extrahera och spara specifika sidor från dina dokument i TIFF-format.