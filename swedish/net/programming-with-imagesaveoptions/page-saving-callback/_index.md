---
title: Sidspara återuppringning
linktitle: Sidspara återuppringning
second_title: Aspose.Words Document Processing API
description: Lär dig hur du anpassar spara dokumentsidor till bilder med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-imagesaveoptions/page-saving-callback/
---

I den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för att använda sidspara-återuppringning med Aspose.Words-bildsparalternativ för .NET. Den här funktionen låter dig utföra anpassade åtgärder när du sparar varje sida i ett dokument som en bild.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 I det här steget konfigurerar vi bildsparalternativen genom att skapa en ny`ImageSaveOptions` objekt. Vi anger önskat backupformat, här "Png" för PNG-formatet. Vi använder`PageSet` för att ange intervallet för sidor som ska sparas, här från första sidan till sista sidan i dokumentet (`doc.PageCount - 1`). Vi ställer också in`PageSavingCallback` till en instans av`HandlePageSavingCallback`, som är en anpassad klass för att hantera sidsparande återuppringning.

## Steg 4: Implementera återuppringning av Spara sida

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implementera dina anpassade åtgärder här
         // Du kan komma åt sidinformation via egenskapen "args.PageIndex".
         // Du kan också ändra sparalternativ för varje sida individuellt
     }
}
```

 I detta steg implementerar vi`HandlePageSavingCallback` klass som implementerar`IPageSavingCallback` gränssnitt. Du kan anpassa den här klassen genom att lägga till dina specifika åtgärder i`PageSaving` metod. Du kan komma åt sidinformation via`args.PageIndex` egendom av`PageSavingArgs` objekt skickas som ett argument.

## Steg 5: Spara sidor som bilder

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 I det här sista steget sparar vi varje sida i dokumentet som en bild med hjälp av`Save` metod och skickar sökvägen till utdatafilen med`.png` tillägg, tillsammans med de angivna sparaalternativen.

Nu kan du köra källkoden för att utföra anpassade åtgärder när du sparar varje sida i dokumentet som en bild. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Exempel på källkod för sidsparande återuppringning med Aspose.Words för .NET


```csharp 
//Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Slutsats

I den här handledningen utforskade vi funktionen för återuppringning av sidan spara med Aspose.Words bildsparalternativ för .NET. Vi lärde oss hur man utför anpassade åtgärder när man sparar varje sida i ett dokument som en bild.

Den här funktionen är användbar när du vill utföra specifika operationer på varje sida när du konverterar till bilder. Du kan komma åt sidinformation och använda den för att anpassa säkerhetskopieringsalternativ eller utföra annan sidspecifik bearbetning.

Aspose.Words för .NET erbjuder ett omfattande utbud av avancerade funktioner för dokumenthantering och generering. Spara sida-påminnelsen är ett av många kraftfulla verktyg som ger dig möjlighet att anpassa processen för att spara sidor till bilder.