---
title: Ställ in alternativa teckensnittsinställningar
linktitle: Ställ in alternativa teckensnittsinställningar
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in inställningar för teckensnittsersättning i Aspose.Words för .NET och anpassa teckensnittsersättning i dina Word-dokument.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-font-fallback-settings/
---
I den här handledningen kommer vi att visa dig hur du ställer in inställningar för teckensnittsersättning i ett Word-dokument med Aspose.Words för .NET. Inställningar för teckensnittsersättning låter dig ange ersättningsteckensnitt som ska användas när de angivna teckensnitten inte är tillgängliga.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
Börja med att ange katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda inställningar för teckensnittsersättning
 Skapa en instans av`FontSettings` klass och använd`Load`metod för att läsa in inställningar för teckensnittsåsidosättning från en XML-fil. Den angivna XML-filen måste innehålla reglerna för teckensnittsersättning som ska användas.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Steg 3: Använd inställningar för teckensnittsersättning
 Koppla inställningar för teckensnittsersättning till dokumentet genom att tilldela dem till dokumentets`FontSettings` fast egendom.

```csharp
doc.FontSettings = fontSettings;
```

## Steg 4: Spara dokumentet
 Spara dokumentet med hjälp av`Save` metod för`Document` med lämplig sökväg och filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Exempel på källkod för Set Font Fallback Settings med Aspose.Words för .NET 
```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Slutsats
I den här handledningen lärde du dig hur du ställer in inställningar för teckensnittsersättning i ett Word-dokument med Aspose.Words för .NET. Experimentera med olika regler för teckensnittsersättning för att säkerställa att ditt dokument ser konsekvent ut, även när de angivna teckensnitten inte är tillgängliga.
