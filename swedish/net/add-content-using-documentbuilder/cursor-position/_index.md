---
title: Markörens position
linktitle: Markörens position
second_title: Aspose.Words Document Processing API
description: Lär dig hur du hämtar markörpositionen i ett Word-dokument med hjälp av Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/cursor-position/
---

det här steg-för-steg-exemplet kommer du att lära dig om markörpositionen i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna hämta den aktuella noden och stycket där markören är placerad i dokumentet.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Gå till den aktuella noden och stycket
Hämta sedan den aktuella noden och stycket där markören är placerad. Detta kan uppnås med hjälp av egenskaperna CurrentNode och CurrentParagraph i klassen DocumentBuilder:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## Steg 3: Hämta markörpositionsinformation
Nu kan du hämta information om markörens position. I följande kodavsnitt skriver vi ut texten i det aktuella stycket:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Exempel på källkod för markörposition med Aspose.Words för .NET
Här är den fullständiga källkoden för att förstå markörens position med Aspose.Words för .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man arbetar med markörposition i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu hämta den aktuella noden och stycket där markören är placerad i dokumentet.

Att förstå markörens position är användbart för olika scenarier, som att manipulera dokumentinnehåll baserat på markörens plats eller implementera anpassade redigeringsfunktioner.

