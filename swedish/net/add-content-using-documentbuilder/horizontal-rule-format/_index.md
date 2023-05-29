---
title: Horisontellt regelformat
linktitle: Horisontellt regelformat
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du formaterar horisontella regler i Word-dokument med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/horizontal-rule-format/
---

det här omfattande exemplet kommer du att lära dig hur du formaterar en horisontell regel i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna anpassa justering, bredd, höjd, färg och andra egenskaper för en horisontell regel.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa en DocumentBuilder och infoga en horisontell regel
För att börja, skapa ett DocumentBuilder-objekt och använd metoden InsertHorizontalRule för att infoga en horisontell regel:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Steg 2: Få åtkomst till det horisontella regelformatet
Gå sedan till egenskapen HorizontalRuleFormat för Shape-objektet för att hämta formateringsalternativen:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Steg 3: Anpassa formateringsalternativen
Nu kan du anpassa olika formateringsalternativ för den horisontella regeln. Du kan till exempel justera justering, bredd, höjd, färg och skuggning:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Steg 4: Spara dokumentet
Efter att ha formaterat den horisontella regeln, spara dokumentet i en fil med hjälp av metoden Spara för dokumentobjektet:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Exempel på källkod för horisontellt regelformat med Aspose.Words för .NET
Här är den fullständiga källkoden för att formatera en horisontell regel med Aspose.Words för .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Kom ihåg att justera koden efter dina specifika krav och utöka den med ytterligare funktionalitet efter behov.

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man formaterar en horisontell regel i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu anpassa utseendet på horisontella regler för att förbättra ditt dokuments visuella layout.

Experimentera med olika formateringsalternativ för att uppnå önskad stil och effekt för dina horisontella regler.
