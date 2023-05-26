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
 Skapa en instans av`Document` klass och en tillhörande`DocumentBuilder` att bygga dokumentinnehållet. Använd`Font.EmphasisMark`egenskap för att ställa in teckensnittets betoningstil till`EmphasisMark.UnderSolidCircle` . Använd sedan`Write` och`Writeln` metoder för`DocumentBuilder` för att lägga till text med den angivna teckensnittets betoning.

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
I den här handledningen lärde du dig hur du ställer in teckensnittets betoningstil i ett Word-dokument med Aspose.Words för .NET. Experimentera med olika stilar av betoning och använd den här funktionen för att markera ord eller fraser i dina dokument.
