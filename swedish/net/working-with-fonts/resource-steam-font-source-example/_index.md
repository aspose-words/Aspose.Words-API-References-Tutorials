---
title: Resurs Steam Font Källa Exempel
linktitle: Resurs Steam Font Källa Exempel
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder Resource Stream Font Source för att ladda anpassade typsnitt till Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/resource-steam-font-source-example/
---

I den här handledningen kommer vi att gå igenom hur du använder Resource Flow Font Source med Aspose.Words för .NET. Denna teckensnittskälla låter dig ladda teckensnitt från en resursström, vilket kan vara användbart när du vill infoga anpassade teckensnitt i din applikation.

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

## Steg 2: Ladda upp dokument och ställ in Resource Stream Font Source
 Därefter laddar vi dokumentet med hjälp av`Document` klass och ställ in resursströmmens teckensnittskälla med hjälp av`FontSettings.DefaultInstance.SetFontsSources()` klass. Detta gör att Aspose.Words kan hitta typsnitten i resursströmmen.

```csharp
// Ladda dokument och ställ in resursströmfontkälla
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Steg 3: Spara dokumentet
Slutligen kommer vi att spara dokumentet. Teckensnitt kommer att laddas från den angivna resursströmmen och bäddas in i dokumentet.

```csharp
// Spara dokumentet
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Exempel på källkod för Resource Steam Font Source Exempel med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Slutsats
I den här handledningen lärde du dig hur du använder Resource Flow Font Source med Aspose.Words för .NET. Den här funktionen låter dig ladda typsnitt från ett resursflöde, vilket är användbart när du vill bädda in anpassade typsnitt i dina dokument. Experimentera med olika typsnitt och utforska de möjligheter som Aspose.Words erbjuder för teckensnittshantering.
