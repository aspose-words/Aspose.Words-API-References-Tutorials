---
title: Punktlista
linktitle: Punktlista
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en punktlista med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/bulleted-list/
---

den här handledningen kommer vi att berätta för dig hur du skapar en punktlista med Aspose.Words för .NET. En punktlista används för att lista objekt utan att använda numrering.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Tillämpa en standard punktlista

 Vi kan använda en standard punktlista med hjälp av dokumentbyggarens`ApplyBulletDefault` metod.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Steg 3: Anpassa Bullet Format

 Vi kan anpassa punktformatet genom att komma åt egenskaperna för`ListFormat.List.ListLevels[0]`. I det här exemplet använder vi bindestrecket "-" som en punkt.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Steg 4: Lägga till objekt i listan

 Nu kan vi lägga till objekt till punktlistan med hjälp av dokumentbyggarens`Writeln` metod.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Steg 5: Ta bort indrag från listan

 Om vi vill skapa en underlista kan vi öka indraget med hjälp av`ListFormat.ListIndent()` metod. I det här exemplet lägger vi till en underlista till punkterna 2a och 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Exempel på källkod för punktlista med Aspose.Words för .NET


```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Grattis! Du har nu lärt dig hur du skapar en punktlista med Aspose.Words för .NET.

### FAQ's

#### F: Hur skapar man en punktlista i Markdown?

S: För att skapa en punktlista i Markdown, starta varje listobjekt med en punktsymbol (`-`, `*` , eller`+`), följt av ett mellanslag.

#### F: Kan du kapsla punktlistor i Markdown?

S: Ja, det är möjligt att kapsla punktlistor i Markdown genom att lägga till fyra offset-mellanslag framför varje kapslad listobjekt.

#### F: Hur anpassar man kulsymboler?

S: I standard Markdown är punktsymboler fördefinierade. Vissa Markdown-redigerare låter dig dock anpassa dem med specifika tillägg.

#### F: Stöder punktlistor i Markdown indrag?

S: Ja, punktlistor i Markdown stöder indrag. Du kan lägga till en vänsterförskjutning med blanksteg eller tabb.

#### F: Kan länkar eller inline-text läggas till i listobjekt?

S: Ja, du kan lägga till länkar eller inline-text till listobjekt med lämplig Markdown-syntax.
