---
title: Insert Break
linktitle: Insert Break
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar sidbrytningar i Word-dokument med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-break/
---

det här omfattande exemplet kommer du att lära dig hur du infogar sidbrytningar i ett Word-dokument med metoden InsertBreak i Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna kontrollera sidbrytningar i ditt dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga innehåll och sidbrytningar
Använd sedan Writeln-metoden i klassen DocumentBuilder för att lägga till innehåll i dokumentet. För att infoga en sidbrytning, använd metoden InsertBreak med parametern BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Steg 3: Spara dokumentet
När du har infogat innehållet och sidbrytningarna sparar du dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Exempel på källkod för Insert Break med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga sidbrytningar med Aspose.Words för .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

Kom ihåg att justera koden efter dina specifika krav och utöka den med ytterligare funktionalitet efter behov.


## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man infogar sidbrytningar i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu kontrollera sidnumreringen och layouten för ditt dokument genom att infoga sidbrytningar på önskade positioner.
