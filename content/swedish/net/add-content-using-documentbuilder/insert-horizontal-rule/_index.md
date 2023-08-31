---
title: Infoga horisontell regel i Word-dokument
linktitle: Infoga horisontell regel i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar horisontella regler i Word-dokument med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
det här omfattande exemplet kommer du att lära dig hur du infogar en horisontell regel i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna lägga till horisontella regler i dina dokument för visuell separation och organisation.

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

### Vanliga frågor för att infoga horisontell regel i word-dokument

#### F: Kan jag anpassa utseendet på den horisontella regeln?

A: Ja, absolut! Aspose.Words för .NET tillhandahåller olika egenskaper för att anpassa utseendet på den horisontella regeln. Du kan justera dess bredd, höjd, justering, färg och skuggning för att matcha dokumentets estetik.

#### F: Kan jag lägga till flera horisontella regler i ett enda dokument?

A: Visst! Du kan infoga så många horisontella regler som behövs i ett Word-dokument med Aspose.Words för .NET. Upprepa helt enkelt infogningsprocessen för att lägga till flera visuella brytningar eller sektionsavdelare.

#### F: Är horisontella regler kompatibla med andra filformat, som PDF?

S: Ja, horisontella regler som infogats med Aspose.Words för .NET är kompatibla med olika filformat, inklusive DOCX och PDF. Det betyder att du kan exportera dina dokument i olika format samtidigt som du behåller de horisontella reglerna.

#### F: Kan jag programmässigt infoga en horisontell regel på specifika positioner i dokumentet?

A: Absolut! Aspose.Words för .NET låter dig placera den horisontella regeln på specifika platser i dokumentet programmatiskt. Du kan styra dess placering baserat på ditt dokuments innehåll och struktur.

#### F: Är Aspose.Words för .NET lämpligt för både skrivbords- och webbapplikationer?

S: Ja, Aspose.Words för .NET är mångsidigt och kan användas i både skrivbords- och webbapplikationer. Oavsett om du bygger en Windows-applikation eller ett webbaserat system, kan du integrera biblioteket utan ansträngning.