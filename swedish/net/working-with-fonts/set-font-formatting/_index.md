---
title: Ställ in teckensnittsformatering
linktitle: Ställ in teckensnittsformatering
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in teckensnittsformatering i Word-dokument med Aspose.Words för .NET och skapar attraktiva dokument.
type: docs
weight: 10
url: /sv/net/working-with-fonts/set-font-formatting/
---
I den här handledningen kommer vi att visa dig hur du ställer in teckensnittsformatering i ett Word-dokument med Aspose.Words för .NET. Du kommer att lära dig hur du använder stilar som fetstil, färg, kursiv stil, teckensnitt, storlek, mellanrum och understrykning.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
Börja med att ange katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa och formatera dokumentet
 Skapa en instans av`Document` klass och`DocumentBuilder` klass för att bygga dokumentet. Använd`Font` egendom av`DocumentBuilder` för att komma åt egenskaper för teckensnittsformatering.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## Steg 3: Spara dokumentet
 Använd`Save` metod för att spara dokumentet med typsnittsformateringen tillämpad. Byta ut`"WorkingWithFonts.SetFontFormatting.docx"` med önskat filnamn.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Exempel på källkod för Set Font Formatting med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Slutsats
Grattis! Du vet nu hur du ställer in teckensnittsformatering i ett Word-dokument med Aspose.Words för .NET. Du kan utforska fler teckensnittsformateringsalternativ och skapa personliga och attraktiva Word-dokument.
