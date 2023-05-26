---
title: Kontrollera DrawingML Text Effect
linktitle: Kontrollera DrawingML Text Effect
second_title: Aspose.Words för .NET API Referens
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
//Ladda dokumentet
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
