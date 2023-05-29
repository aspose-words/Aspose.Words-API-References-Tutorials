---
title: Document Builder Infoga bokmärke
linktitle: Document Builder Infoga bokmärke
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar bokmärken i Word-dokument med DocumentBuilder i Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

det här omfattande exemplet kommer du att lära dig hur du infogar bokmärken i ett Word-dokument med klassen DocumentBuilder i Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna skapa och hantera bokmärken i dina dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga ett bokmärke
Använd sedan metoderna StartBookmark och EndBookmark i klassen DocumentBuilder för att infoga ett bokmärke i dokumentet. Ange ett unikt namn för bokmärket som en parameter:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Steg 3: Spara dokumentet
När du har infogat bokmärket, spara dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Exempel på källkod för DocumentBuilder Infoga bokmärke med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga ett bokmärke med klassen DocumentBuilder i Aspose.Words för .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du infogar bokmärken i ett Word-dokument med klassen DocumentBuilder i Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu skapa och hantera bokmärken i dina dokument.

Bokmärken är användbara för olika scenarier, som att navigera genom stora dokument, hänvisa till specifika avsnitt eller programmatiskt manipulera innehåll inom bokmärkta områden.

Kom ihåg att justera koden efter dina specifika krav och utöka den med ytterligare funktionalitet efter behov.

