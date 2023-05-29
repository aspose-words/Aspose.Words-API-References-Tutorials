---
title: Genomstruken
linktitle: Genomstruken
second_title: Aspose.Words för .NET API Referens
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
