---
title: Kursiv text
linktitle: Kursiv text
second_title: Aspose.Words Document Processing API
description: Lär dig att kursiv text med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/italic-text/
---

I det här exemplet kommer vi att gå igenom hur du använder kursiv text med Aspose.Words för .NET. Kursiv text används för att framhäva vissa delar av ett dokument.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Kursivera text

 Vi kan kursivera text genom att ställa in typsnittets`Italic` egendom till`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Exempel på källkod för kursiv text med Aspose.Words för .NET


```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

// Gör texten kursiv.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Grattis! Du har nu lärt dig hur du använder kursiv text med Aspose.Words för .NET.


### FAQ's

#### F: Hur kan jag kursivera text i Aspose.Words?

S: För att kursivera text i Aspose.Words kan du använda`Font.Italic`egendom av`Run`objekt. Du kan ställa in den här egenskapen till`true` för att kursivera specifik text. Du kan till exempel använda`run.Font.Italic=true` för att kursivera texten i`Run` objekt.

#### F: Är det möjligt att kursivera flera stycken text i samma stycke?

 S: Ja, du kan kursivera flera stycken text i ett enda stycke med hjälp av flera`Run` föremål. Du kan skapa flera`Run` objekt och ställ in`Font.Italic` egendom till`true` för varje objekt att kursivera önskade delar av texten. Sedan kan du lägga till dem i stycket med hjälp av`Paragraph.AppendChild(run)` metod.

#### F: Kan jag kursivera text som finns i en tabell eller cell i Aspose.Words?

 S: Ja, du kan kursivera text som finns i en tabell eller cell i Aspose.Words. Du kan navigera till cellen eller stycket du vill använda med lämpliga metoder och sedan använda kursiv formatering med hjälp av`Font.Italic`egendom av`Run` eller`Paragraph` objekt.