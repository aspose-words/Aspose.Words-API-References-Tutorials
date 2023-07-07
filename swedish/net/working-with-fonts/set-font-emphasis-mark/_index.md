---
title: Ställ in teckensnittsbetoning
linktitle: Ställ in teckensnittsbetoning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in teckensnittets betoningstil i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-font-emphasis-mark/
---

I den här handledningen kommer vi att visa dig hur du ställer in teckensnittets betoningstil i ett Word-dokument med Aspose.Words för .NET. Typsnittsbetoning används för att markera vissa ord eller fraser i text.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
 Börja med att ange katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa och anpassa dokumentet
 Skapa en instans av`Document` klass och en tillhörande`DocumentBuilder` att bygga dokumentinnehållet. Använd`Font.EmphasisMark` egenskap för att ställa in teckensnittets betoningstil till`EmphasisMark.UnderSolidCircle` . Använd sedan`Write` och`Writeln` metoder för`DocumentBuilder` för att lägga till text med den angivna teckensnittets betoning.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Steg 3: Spara dokumentet
 Spara dokumentet med hjälp av`Save` metod för`Document` med lämplig sökväg och filnamn.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Exempel på källkod för Set Font Emhasis Mark med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Slutsats
den här handledningen lärde du dig hur du ställer in teckensnittets betoningstil i ett Word-dokument med Aspose.Words för .NET. Experimentera med olika stilar av betoning och använd den här funktionen för att markera ord eller fraser i dina dokument.

### FAQ's

#### F: Hur kan jag lägga till accenttecken till ett specifikt teckensnitt i ett Word-dokument med Aspose.Words?

S: För att lägga till accenttecken till ett specifikt teckensnitt i ett Word-dokument med Aspose.Words kan du använda API:et för att navigera till önskat teckensnitt och använda lämpliga accenttecken. Detta kommer att lägga till accenttecken i texten med det valda teckensnittet.

#### F: Är det möjligt att ändra stilen på accenttecken i ett Word-dokument med Aspose.Words?

S: Ja, med Aspose.Words kan du ändra stilen på accenttecken i ett Word-dokument. API:et låter dig justera stilegenskaper som färg, storlek, linjetyp, etc., för att anpassa utseendet på accentmärken.

#### F: Hur kan jag ta bort alla accenttecken från ett Word-dokument med Aspose.Words?

S: För att ta bort alla accenttecken från ett Word-dokument med Aspose.Words kan du använda API:et för att bläddra i dokumentet, upptäcka befintliga accenttecken och ta bort dem med lämpliga metoder. Detta tar bort alla betoningsmärken från dokumentet.

#### F: Kan jag lägga till accenttecken på en specifik del av texten i ett Word-dokument?

S: Ja, du kan lägga till accenttecken på en specifik del av texten i ett Word-dokument med Aspose.Words. Du kan välja önskat textområde med hjälp av API:et och lägga till lämpliga betoningstecken på den delen av texten.

#### F: Kan accentmärkena anpassas efter mina behov?

S: Ja, accenttecken kan anpassas efter dina behov med Aspose.Words. Du kan justera stilegenskaperna för accentmärken, som färg, storlek, linjetyp med mera, för att matcha dina formateringspreferenser.