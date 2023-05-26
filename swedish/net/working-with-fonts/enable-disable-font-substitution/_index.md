---
title: Aktivera Inaktivera teckensnittsersättning
linktitle: Aktivera Inaktivera teckensnittsersättning
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen lär du dig hur du aktiverar eller inaktiverar teckensnittsersättning i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/enable-disable-font-substitution/
---
den här handledningen går vi igenom hur du aktiverar eller inaktiverar teckensnittsersättning i ett Word-dokument när du renderar det med Aspose.Words-biblioteket för .NET. Genom att aktivera eller inaktivera teckensnittsersättning kan du kontrollera om saknade teckensnitt automatiskt ersätts med ett standardteckensnitt. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som du vill rendera med eller utan teckensnittsersättning

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda upp dokumentet och konfigurera teckensnittsinställningarna
 Därefter laddar vi Word-dokumentet du vill rendera och skapar en instans av`FontSettings` klass för att hantera teckensnittsinställningarna. Vi ställer in standardtypsnittets åsidosättande genom att ange teckensnittsnamnet i`DefaultFontName` och inaktivera åsidosättande av teckensnittsinformation med`Enabled` satt till`false`.

```csharp
//Ladda dokumentet
Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurera teckensnittsinställningar
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Tillämpa teckensnittsinställningarna på dokumentet
doc.FontSettings = fontSettings;
```

## Steg 3: Spara det renderade dokumentet
Slutligen kommer vi att spara det renderade dokumentet, vilket kommer att respektera de definierade inställningarna för teckensnittsåsidosättning.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Exempel på källkod för Aktivera inaktivera teckensnittsersättning med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Slutsats
I den här handledningen såg vi hur du aktiverar eller inaktiverar teckensnittsersättning i ett Word-dokument när du renderar det med Aspose.Words för .NET. Genom att kontrollera teckensnittsersättning kan du påverka hur saknade teckensnitt hanteras i dina renderade dokument. Tveka inte att använda den här funktionen för att anpassa hanteringen av teckensnitt i dina Word-dokument.