---
title: Kursiv text
linktitle: Kursiv text
second_title: Aspose.Words för .NET API Referens
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

