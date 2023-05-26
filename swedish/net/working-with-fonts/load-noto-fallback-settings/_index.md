---
title: Ladda Noto reservinställningar
linktitle: Ladda Noto reservinställningar
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen lär du dig hur du laddar Noto-överstyrningsparametrar i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/load-noto-fallback-settings/
---
den här handledningen går vi igenom hur du laddar in inställningar för Noto-teckensnittsersättning i ett Word-dokument med hjälp av Aspose.Words Library för .NET. Inställningarna för Noto Font Substitution låter dig hantera ersättningen av teckensnitt när du visar eller skriver ut dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

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

## Steg 2: Ladda dokumentet och konfigurera inställningar för teckensnittsersättning
 Därefter laddar vi dokumentet med hjälp av`Document` klass och konfigurera inställningarna för teckensnittsåsidosättning med hjälp av`FontSettings` klass. Vi kommer att ladda Noto-typsnittets reservinställningar med hjälp av`LoadNotoFallbackSettings()` metod.

```csharp
// Ladda dokumentet och konfigurera inställningar för teckensnittsersättning
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## Steg 3: Spara dokumentet
Slutligen kommer vi att spara dokumentet med Noto teckensnittsersättningsinställningar tillämpade.

```csharp
// Spara dokumentet
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### Exempel på källkod för Noto Fallback-inställningar med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## Slutsats
den här handledningen såg vi hur man laddar Noto-fontersättningsinställningar i ett Word-dokument med Aspose.Words för .NET. Med inställningarna för ersättning av teckensnitt i Noto kan du hantera teckensnittsersättning för att förbättra visningen och utskriften av dina dokument. Använd gärna den här funktionen för att anpassa teckensnittsersättningen efter dina behov.