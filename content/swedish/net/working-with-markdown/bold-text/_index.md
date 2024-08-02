---
title: Fettext
linktitle: Fettext
second_title: Aspose.Words Document Processing API
description: Lär dig hur du gör fet text med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/bold-text/
---

I det här exemplet kommer vi att berätta för dig hur du gör fet text med Aspose.Words för .NET. Fet text gör den mer synlig och ger den mer framträdande plats.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Fet text

 Vi kan feta texten genom att ställa in dokumentbyggarens`Font.Bold`egendom till`true`.

```csharp
builder.Font.Bold = true;
```

## Steg 3: Lägg till innehåll i dokumentet

 Nu kan vi lägga till innehåll i dokumentet med hjälp av dokumentbyggarmetoderna, som t.ex`Writeln`, som lägger till en textrad.

```csharp
builder.Writeln("This text will be bold");
```

## Exempel på källkod för fet text med Aspose.Words för .NET


```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

// Gör texten fet.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Grattis! Du har nu lärt dig hur man fet text med Aspose.Words för .NET.


### FAQ's

#### F: Hur kan jag göra text fet i Aspose.Words?

 S: För att göra text fet i Aspose.Words kan du använda`Font.Bold` egendom av`Run` objekt. Du kan ställa in den här egenskapen till`true` till fet specifik text. Du kan till exempel använda`run.Font.Bold=true` för att feta texten inuti`Run` objekt.

#### F: Är det möjligt att feta flera stycken text i samma stycke?

 S: Ja, du kan feta flera stycken text i ett enda stycke med hjälp av flera`Run` föremål. Du kan skapa flera`Run` objekt och ställ in`Font.Bold`egendom till`true` för varje objekt att feta de önskade textdelarna. Sedan kan du lägga till dem i stycket med hjälp av`Paragraph.AppendChild(run)` metod.

#### F: Kan jag fet text som finns i en tabell eller cell i Aspose.Words?

 S: Ja, du kan fet text som finns i en tabell eller cell i Aspose.Words. Du kan navigera till cellen eller stycket du vill använda med lämpliga metoder och sedan tillämpa den fetstilta formateringen med hjälp av`Font.Bold` egendom av`Run` eller`Paragraph` objekt.