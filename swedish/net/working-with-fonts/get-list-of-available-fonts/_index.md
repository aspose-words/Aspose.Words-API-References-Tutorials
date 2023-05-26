---
title: Få lista över tillgängliga teckensnitt
linktitle: Få lista över tillgängliga teckensnitt
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen kan du lära dig hur du får en lista över teckensnitt som är tillgängliga i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/get-list-of-available-fonts/
---
den här handledningen kommer vi att förklara hur du får en lista över teckensnitt som är tillgängliga i Aspose.Words för .NET. Listan över tillgängliga teckensnitt låter dig veta vilka teckensnitt du kan använda i dina dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Konfigurera teckensnittskällor
 Därefter skapar vi en instans av`FontSettings` och hämta de befintliga teckensnittskällorna med hjälp av`GetFontsSources()` metod. Vi kommer också att lägga till en ny typsnittskälla genom att ange en mapp som innehåller typsnitt.

```csharp
// Konfigurera teckensnittskällor
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Lägg till en ny teckensnittskälla
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Steg 3: Hämta listan över tillgängliga teckensnitt
 Nu kommer vi att bläddra bland de tillgängliga typsnitten med hjälp av`GetAvailableFonts()` metod på den första uppdaterade teckensnittskällan.

```csharp
// Få en lista över tillgängliga typsnitt
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Exempel på källkod för Hämta lista över tillgängliga teckensnitt med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Lägg till en ny mappkälla som instruerar Aspose.Words att söka efter typsnitt i följande mapp.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Lägg till den anpassade mappen som innehåller våra typsnitt till listan över befintliga teckensnittskällor.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Slutsats
den här handledningen såg vi hur man får listan över teckensnitt som är tillgängliga i Aspose.Words för .NET. Detta låter dig veta vilka typsnitt du kan använda i dina dokument. Använd gärna den här funktionen för att välja lämpliga typsnitt för dina behov.