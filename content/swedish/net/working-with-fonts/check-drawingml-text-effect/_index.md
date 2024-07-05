---
title: Kontrollera DrawingML Text Effect
linktitle: Kontrollera DrawingML Text Effect
second_title: Aspose.Words Document Processing API
description: I den här handledningen lär du dig hur du kontrollerar DrawingML-texteffekter i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/check-drawingml-text-effect/
---

I den här handledningen går vi igenom hur du kontrollerar DrawingML-texteffekter i ett Word-dokument med Aspose.Words Library för .NET. Genom att markera DrawingML-texteffekter kan du avgöra om en specifik effekt tillämpas på en del av texten. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som innehåller DrawingML-texteffekter

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet och kontrollera texteffekterna
Därefter laddar vi Word-dokumentet och kommer åt samlingen av körningar (teckensekvenser) i det första stycket i dokumentets brödtext. Därefter kontrollerar vi om några specifika DrawingML-texteffekter tillämpas på teckensnittet för den första körningen.

```csharp
// Ladda dokumentet
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Kontrollera DrawingML-texteffekter
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Exempel på källkod för Check DMLText Effect med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// En körning kan ha flera Dml-texteffekter tillämpade.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Slutsats
I den här handledningen såg vi hur man kontrollerar DrawingML-texteffekter i ett Word-dokument med Aspose.Words för .NET. Genom att markera DrawingML-texteffekter kan du identifiera delar av text som har specifika effekter tillämpade. Använd gärna den här funktionen för att manipulera och analysera texteffekter i dina Word-dokument.

### FAQ's

#### F: Hur kan jag komma åt DrawingML-texteffekter i ett Word-dokument med Aspose.Words?

S: Med Aspose.Words kan du komma åt DrawingML-texteffekter i ett Word-dokument med hjälp av det medföljande API:et. Du kan bläddra i textelement och kontrollera specifika egenskaper för texteffekter, såsom färg, storlek, etc.

#### F: Vilka typer av DrawingML-texteffekter används vanligtvis i Word-dokument?

S: Vanliga typer av DrawingML-texteffekter i Word-dokument inkluderar skuggor, reflektioner, glöd, gradienter, etc. Dessa effekter kan användas för att förbättra utseendet och formateringen av text.

#### F: Hur kan jag kontrollera färgen på en DrawingML-texteffekt i ett Word-dokument?

S: För att kontrollera färgen på en DrawingML-texteffekt i ett Word-dokument kan du använda metoderna som tillhandahålls av Aspose.Words för att komma åt texteffektens färgegenskaper. På så sätt kan du få färgen som används för den specifika texteffekten.

#### F: Är det möjligt att kontrollera texteffekter i Word-dokument som innehåller flera avsnitt?

S: Ja, Aspose.Words tillåter kontroll av texteffekter i Word-dokument som innehåller flera avsnitt. Du kan navigera genom varje avsnitt i dokumentet och få tillgång till texteffekter för varje avsnitt individuellt.

#### F: Hur kan jag kontrollera opaciteten för en DrawingML-texteffekt i ett Word-dokument?

S: För att kontrollera opaciteten för en DrawingML-texteffekt i ett Word-dokument kan du använda metoderna som tillhandahålls av Aspose.Words för att komma åt opacitetsegenskaperna för texteffekten. Detta gör att du kan få opacitetsvärdet applicerat på den specifika texteffekten.