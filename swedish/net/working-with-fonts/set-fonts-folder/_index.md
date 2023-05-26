---
title: Ställ in typsnittsmapp
linktitle: Ställ in typsnittsmapp
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in teckensnittskatalogen i Aspose.Words för .NET och se till att teckensnitt som används i dina dokument är tillgängliga.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-fonts-folder/
---
I den här handledningen kommer vi att visa dig hur du ställer in typsnittskatalogen i Aspose.Words för .NET. Du kommer att lära dig hur du anger katalogen som innehåller teckensnitten som används i ditt Word-dokument.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
Börja med att ange katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ställ in teckensnittskatalog
 Skapa en instans av`FontSettings` klass och använd`SetFontsFolder` metod för att ange katalogen som innehåller typsnitten. Byta ut`"Fonts"` med namnet på den faktiska teckensnittskatalogen.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Steg 3: Ladda dokumentet med teckensnittsinställningar
 Använd`LoadOptions` klass för att ange teckensnittsinställningar i`FontSettings` alternativ. Använd sedan`Document` klass för att ladda dokumentet med dessa alternativ.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Exempel på källkod för Set Fonts Folder med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Slutsats
Grattis! Du vet nu hur du ställer in typsnittskatalogen i Aspose.Words för .NET. Du kan använda den här funktionen för att säkerställa tillgängligheten för teckensnitt som används i ditt dokument och för att säkerställa konsekvens i visningen av teckensnitt.
