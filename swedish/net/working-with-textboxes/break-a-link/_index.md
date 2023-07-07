---
title: Bryt länken framåt i Word-dokument
linktitle: Bryt länken framåt i Word-dokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du bryter fram länkar i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-textboxes/break-a-link/
---

Aspose.Words för .NET är ett kraftfullt bibliotek som erbjuder olika funktioner för att arbeta med Microsoft Word-dokument programmatiskt. En av dess användbara funktioner är möjligheten att bryta fram länkar i ett word-dokument. I den här handledningen kommer vi att utforska källkoden i C# som visar hur man bryter länken framåt i Word-dokument med Aspose.Words för .NET.

## Steg 1: Förhandsgranskning av C#-källkod

Den medföljande C#-källkoden fokuserar på "Break A Link"-funktionen i Aspose.Words för .NET. Den visar hur man bryter en länk i en TextBox-form inuti ett dokument. Koden presenterar olika scenarier för att bryta länkar och ger tydliga instruktioner om hur man uppnår önskade resultat.

## Steg 2: Konfigurera dokumentet och skapa en TextBox-form

För att börja måste vi ställa in dokumentet och skapa en TextBox-form. Följande kod initierar en ny instans av`Document` klass och skapar en textrutaform:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Steg 3: Bryt fram länken i TextBox

 För att bryta en framåtlänk i textrutan kan vi använda`BreakForwardLink()` metod. Denna metod bryter länken till nästa form i sekvensen. Följande kod visar hur man bryter en framåtlänk:

```csharp
textBox.BreakForwardLink();
```

## Steg 4: Bryt en framåtlänk genom att ställa in ett nollvärde

 Alternativt kan vi bryta en framåtlänk genom att ställa in textrutan`Next` egendom till`null`. Detta tar effektivt bort kopplingen till nästa form. Följande kod visar detta tillvägagångssätt:

```csharp
textBox. Next = null;
```

## Steg 5: Bryt en länk som leder till textrutan

 I vissa fall måste vi bryta en länk som leder till TextBox-formen. Vi kan uppnå detta genom att ringa till`BreakForwardLink()` metod på`Previous` form, som bryter länken till textrutan. Här är ett exempel på hur man bryter en sådan länk:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Exempel på källkod för att bryta en länk med Aspose.Words för .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Bryt länken framåt.
textBox.BreakForwardLink();

//Bryt en framåtlänk genom att ställa in ett nollvärde.
textBox. Next = null;

// Bryt en länk som leder till den här textrutan.
textBox.Previous?.BreakForwardLink();
```

## Slutsats

Grattis! Du har nu lärt dig hur du bryter omdirigeringslänkar i ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Genom att följa stegen i den här guiden kunde du ställa in dokumentet, skapa en TextBox-form och bryta omdirigeringslänkarna med olika metoder.

### Vanliga frågor om bryta framåt länk i word-dokument

#### F: Vilket bibliotek används för att bryta omdirigeringslänkar i ett Word-dokument med Aspose.Words för .NET?

S: För att bryta omdirigeringslänkar i ett Word-dokument med Aspose.Words för .NET, är biblioteket som används Aspose.Words for .NET.

#### F: Hur bryter man en omdirigeringslänk i en textruta?

 S: För att bryta en framåtlänk i en textruta kan du använda`BreakForwardLink()` metod. Denna metod bryter länken till nästa form i sekvensen.

#### F: Hur bryter man en omdirigeringslänk genom att ställa in ett nollvärde?

 S: Alternativt kan du bryta en omdirigeringslänk genom att ställa in`Next`egenskapen för textrutan till`null`. Detta tar effektivt bort kopplingen till nästa form.

#### F: Hur bryter man en länk som leder till textrutan?

 S: I vissa fall måste du bryta en länk som leder till textrutan. Du kan uppnå detta genom att ringa till`BreakForwardLink()` metod på`Previous` form, som bryter länken till textrutan.

#### F: Kan vi bryta omdirigeringslänkar på andra element än TextBoxes?

S: Ja, med Aspose.Words för .NET är det möjligt att bryta omdirigeringslänkar på olika element som stycken, tabeller, bilder etc. Processen kan variera beroende på det specifika objektet du vill bryta länken på.