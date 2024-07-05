---
title: Genomstruken
linktitle: Genomstruken
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder den genomstrukna textstilen med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/strikethrough/
---


I det här exemplet kommer vi att gå igenom hur du tillämpar den genomstrukna textstilen med Aspose.Words för .NET. Genomstruken text används för att indikera att texten är raderad eller inte längre giltig.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Använd genomstruken textstil

Vi kommer att aktivera den genomstrukna textstilen genom att ställa in`StrikeThrough` egendom av`Font` invända mot`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Steg 3: Lägg till genomstruken text

 Vi kan nu lägga till genomstruken text med hjälp av dokumentgeneratorns`Writeln` metod.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Exempel på källkod för genomstruken text med Aspose.Words för .NET

```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

// Gör texten genomstruken.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Grattis! Du har nu lärt dig hur du använder den genomstrukna textstilen med Aspose.Words för .NET.

### FAQ's

#### F: Hur kan jag lägga till den genomstrukna texten i Aspose.Words?

 S: För att lägga till den genomstrukna texten i Aspose.Words kan du använda`Font.StrikeThrough` egendom av`Run`objekt. Du kan ställa in den här egenskapen till`true` för att lägga till genomstruken text till specifik text. Du kan till exempel använda`run.Font.StrikeThrough=true` för att lägga till den genomstrukna texten i`Run` objekt.

#### F: Är det möjligt att lägga till den genomstrukna texten i flera textstycken i samma stycke?

 S: Ja, du kan lägga till genomstruken text i flera delar av texten i ett enda stycke genom att använda flera`Run` föremål. Du kan skapa flera`Run` objekt och ställ in`Font.StrikeThrough`egendom till`true` för varje objekt för att lägga till den genomstrukna texten till de önskade textdelarna. Sedan kan du lägga till dem i stycket med hjälp av`Paragraph.AppendChild(run)` metod.

#### F: Kan jag lägga till genomstruken text till text som finns i en tabell eller cell i Aspose.Words?

 S: Ja, du kan lägga till genomstruken text till text som finns i en tabell eller cell i Aspose.Words. Du kan hoppa till cellen eller stycket du vill använda med lämpliga metoder och sedan tillämpa den genomstrukna textformateringen med hjälp av`Font.StrikeThrough` egendom av`Run` eller`Paragraph` objekt.