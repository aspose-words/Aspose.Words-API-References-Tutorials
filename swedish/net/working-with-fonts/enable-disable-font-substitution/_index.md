---
title: Aktivera Inaktivera teckensnittsersättning
linktitle: Aktivera Inaktivera teckensnittsersättning
second_title: Aspose.Words för .NET API Referens
description: den här handledningen lär du dig hur du aktiverar eller inaktiverar teckensnittsersättning i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/enable-disable-font-substitution/
---
I den här handledningen går vi igenom hur du aktiverar eller inaktiverar teckensnittsersättning i ett Word-dokument när du renderar det med Aspose.Words-biblioteket för .NET. Genom att aktivera eller inaktivera teckensnittsersättning kan du kontrollera om saknade teckensnitt automatiskt ersätts med ett standardteckensnitt. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

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

### FAQ's

#### F: Hur kan jag aktivera teckensnittsersättning i ett Word-dokument med Aspose.Words?

S: För att möjliggöra teckensnittsersättning i ett Word-dokument med Aspose.Words kan du använda API:et för att ange ersättningsteckensnitt som ska användas när nödvändiga teckensnitt inte är tillgängliga. Detta kommer att säkerställa konsekvent textvisualisering, även utan de ursprungliga teckensnitten.

#### F: Är det möjligt att inaktivera teckensnittsersättning i ett Word-dokument med Aspose.Words?

S: Ja, med Aspose.Words kan du inaktivera teckensnittsersättning i ett Word-dokument. Genom att använda API:t kan du förhindra att Word ersätter nödvändiga teckensnitt med andra teckensnitt, vilket behåller textens ursprungliga utseende.

#### F: Vad händer när obligatoriska teckensnitt saknas under ersättning i ett Word-dokument?

S: När nödvändiga teckensnitt saknas under ersättning i ett Word-dokument, kan Aspose.Words upptäcka detta problem och ge dig alternativ för att åtgärda det. Du kan välja att ersätta saknade teckensnitt med alternativa teckensnitt eller inkludera saknade teckensnitt i dokumentet, vilket säkerställer korrekt visning.

#### F: Hur kan jag hantera saknade teckensnitt när jag ersätter i ett Word-dokument med Aspose.Words?

S: För att hantera saknade teckensnitt när du ersätter ett Word-dokument med Aspose.Words, kan du använda API:et för att upptäcka saknade teckensnitt och tillhandahålla upplösningsalternativ. Du kan välja att ersätta saknade teckensnitt med alternativa teckensnitt eller inkludera saknade teckensnitt i dokumentet, beroende på dina behov.

#### F: Är det viktigt att kontrollera teckensnittsersättning i ett Word-dokument?

S: Ja, det är viktigt att kontrollera teckensnittsersättning i ett Word-dokument för att bibehålla textens visuella integritet. Genom att använda Aspose.Words för att aktivera eller inaktivera teckensnittsersättning kan du säkerställa att de nödvändiga teckensnitten används och undvika problem med saknade eller ersatta teckensnitt.