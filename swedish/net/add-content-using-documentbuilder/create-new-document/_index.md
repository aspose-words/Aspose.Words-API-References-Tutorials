---
title: Skapa nytt dokument
linktitle: Skapa nytt dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar ett nytt Word-dokument och lägger till innehåll med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/create-new-document/
---

denna steg-för-steg handledning kommer du att lära dig hur du skapar ett nytt Word-dokument från grunden med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna skapa ett nytt dokument och lägga till innehåll till det med klassen DocumentBuilder.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument
För att börja skapa ett nytt dokument med klassen Document:

```csharp
Document doc = new Document();
```

## Steg 2: Lägg till innehåll i dokumentet
Använd sedan ett DocumentBuilder-objekt för att lägga till innehåll i dokumentet. Initiera DocumentBuilder med det nyskapade dokumentet:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## Steg 3: Spara dokumentet
När du har lagt till önskat innehåll, spara dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Exempel på källkod för att skapa ett nytt dokument med Aspose.Words för .NET
Här är den fullständiga källkoden för att skapa ett nytt dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document();

// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du skapar ett nytt Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guiden och använda den medföljande källkoden kan du nu generera nya dokument programmatiskt och lägga till innehåll till dem med klassen DocumentBuilder.

Nu kan du tryggt skapa och anpassa Word-dokument enligt dina specifika krav.

### Exempel på källkod för att skapa ett nytt dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document();

// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

Kom ihåg att justera sökvägen och namnet i koden för att spara dokumentet på önskad plats på ditt system.

