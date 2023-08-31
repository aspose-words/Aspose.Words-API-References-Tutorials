---
title: Hämta teckensnittsradavstånd
linktitle: Hämta teckensnittsradavstånd
second_title: Aspose.Words Document Processing API
description: I den här handledningen lär du dig hur du får teckensnittsradavstånd i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/get-font-line-spacing/
---
den här handledningen kommer vi att berätta hur du får typsnittets radavstånd i ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Teckensnittets radavstånd definierar det vertikala avståndet mellan textraderna. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Skapa ett nytt dokument och dokumentgenerator
 Först skapar vi ett nytt dokument genom att instansiera`Document` klass och en dokumentbyggare genom att instansiera`DocumentBuilder` klass.

```csharp
// Skapa ett nytt dokument
Document doc = new Document();

//Skapa en dokumentgenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Konfigurera typsnittet
 Därefter kommer vi att konfigurera teckensnittet genom att ställa in`Name` dokumentgeneratorns egendom.

```csharp
// Konfigurera typsnittet
builder.Font.Name = "Calibri";
```

## Steg 3: Lägg till text i dokumentet
Vi kommer nu att använda dokumentgeneratorn för att lägga till formaterad text till dokumentet.

```csharp
// Lägg till text i dokumentet
builder. Writen("qText");
```

## Steg 4: Hämta teckensnittsradavstånd
 Nu kommer vi åt`Font` föremål för första stycket i dokumentet och hämta värdet av`LineSpacing` fast egendom.

```csharp
// Hämta teckensnittets radavstånd
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Exempel på källkod för Get Font Line Spacing med Aspose.Words för .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Slutsats
den här handledningen såg vi hur man får typsnittets radavstånd i ett Word-dokument med Aspose.Words för .NET. Teckensnittets radavstånd är viktigt för att kontrollera det vertikala avståndet mellan textrader. Använd gärna den här funktionen för att anpassa utseendet på din text i dina dokument.

### FAQ's

#### F: Hur kan jag ändra radavståndet för specifik text i ett Word-dokument?

S: Med Aspose.Words kan du enkelt ändra radavståndet för specifik text i ett Word-dokument. Använd API:et för att välja önskad text och justera avståndet mellan raderna genom att ange lämpligt värde.

#### F: Är det möjligt att använda exakt avstånd mellan rader i ett Word-dokument?

S: Ja, Aspose.Words låter dig tillämpa exakt avstånd mellan raderna i ett Word-dokument. Du kan ange ett exakt värde för radavstånd med hjälp av API:et.

#### F: Hur kan jag justera radavståndet för hela Word-dokumentet?

S: Med Aspose.Words kan du enkelt justera radavståndet för hela Word-dokumentet. Använd metoderna som tillhandahålls av API:et för att ange önskat radavstånd för hela dokumentet.

#### F: Stöder Aspose.Words flera radavstånd?

S: Ja, Aspose.Words stöder flera radavstånd i Word-dokument. Du kan ställa in flera avstånd, till exempel 1,5 gånger eller 2 gånger normalt avstånd, för raderna i din text.

#### F: Hur kan jag undvika problem med radöverlappning när jag justerar radavstånd?

S: För att undvika problem med linjeöverlappning när du justerar avståndet mellan raderna, var noga med att välja lämpliga avståndsvärden. Testa även den slutliga renderingen av ditt dokument för att säkerställa att texten förblir läsbar och välformaterad.