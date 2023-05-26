---
title: Öppna Typfunktioner
linktitle: Öppna Typfunktioner
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du aktiverar och använder Open Type-funktioner i Aspose.Words för .NET
type: docs
weight: 10
url: /sv/net/enable-opentype-features/open-type-features/
---

I den här omfattande handledningen kommer du att lära dig hur du aktiverar och använder Open Type-funktioner i Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna arbeta med Open Type-funktioner i dina Word-dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Ladda dokumentet
För att börja, ladda dokumentet med klassen Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Steg 2: Aktivera Open Type-funktioner
För att aktivera Open Type-funktioner, ställ in egenskapen TextShaperFactory för klassen LayoutOptions till en instans av önskad textformningsfabrik. I det här exemplet använder vi HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Steg 3: Spara dokumentet
När du har aktiverat Open Type-funktionerna sparar du dokumentet i önskat utdataformat, till exempel PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Exempel på källkod för Open Type-funktioner med Aspose.Words för .NET
Här är den fullständiga källkoden för användning av Open Type-funktioner i Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du aktiverar och använder Open Type-funktioner i Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu arbeta med Open Type-funktioner i dina Word-dokument.

Open Type-funktioner erbjuder förbättrade typografi- och textformningsfunktioner, så att du kan skapa visuellt tilltalande och professionella dokument. Experimentera med olika textformningsfabriker och utforska möjligheterna med Open Type-funktioner i dina projekt.
