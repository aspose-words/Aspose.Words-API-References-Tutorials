---
title: Horisontell regel
linktitle: Horisontell regel
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar en horisontell regel med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/horizontal-rule/
---

I det här exemplet kommer vi att visa dig hur du använder den horisontella regelfunktionen med Aspose.Words för .NET. Horisontella regler används för att visuellt separera delar av ett dokument.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Infoga en horisontell regel

 Vi kan infoga en horisontell regel med hjälp av`InsertHorizontalRule` dokumentgeneratorns metod.

```csharp
builder. InsertHorizontalRule();
```

## Exempel på källkod för horisontell regel med Aspose.Words för .NET

```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

// Infoga horisontell regel.
builder.InsertHorizontalRule();
```

Grattis! Du har nu lärt dig hur du använder den horisontella regelfunktionen med Aspose.Words för .NET.


### FAQ's

#### F: Hur skapar jag en horisontell linjal i Markdown?

S: För att skapa en horisontell linjal i Markdown kan du använda en av följande symboler på en tom rad: tre asterisker (\***), tre streck (\---), eller tre understreck (\___).

#### F: Kan jag anpassa utseendet på en horisontell linjal i Markdown?

S: I standard Markdown finns det inget sätt att anpassa utseendet på horisontella linjaler. Vissa avancerade Markdown-redigerare och tillägg erbjuder dock ytterligare anpassningsfunktioner.

#### F: Stöds horisontella linjaler av alla Markdown-redigerare?

S: Ja, de flesta populära Markdown-redigerare stöder horisontella linjaler. Det är dock alltid bäst att kontrollera din specifika leverantörs dokumentation för att se till att den stöds.

#### F: Vilka andra element kan jag skapa i Markdown?

S: Förutom horisontella linjaler kan du skapa titlar, stycken, listor, länkar, bilder, tabeller och mer i Markdown.