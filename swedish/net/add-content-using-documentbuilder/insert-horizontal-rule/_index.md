---
title: Infoga horisontell regel
linktitle: Infoga horisontell regel
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar horisontella regler i Word-dokument med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

I det här omfattande exemplet kommer du att lära dig hur du infogar en horisontell regel i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna lägga till horisontella regler i dina dokument för visuell separation och organisation.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga en horisontell regel
Använd sedan Writeln-metoden i klassen DocumentBuilder för att lägga till en beskrivande text och infoga sedan en horisontell regel:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Steg 3: Spara dokumentet
När du har infogat den horisontella regeln, spara dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Exempel på källkod för Infoga horisontell regel med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga en horisontell regel med Aspose.Words för .NET:
Horisontella regler är användbara för olika scenarier, som att dela upp avsnitt, skapa visuella avbrott eller framhäva viktig information.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Kom ihåg att justera koden efter dina specifika krav och utöka den med ytterligare funktionalitet efter behov.

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man infogar en horisontell regel i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu visuellt separera och organisera dina dokument med horisontella regler.

