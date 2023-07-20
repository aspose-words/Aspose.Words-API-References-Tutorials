---
title: Horisontellt regelformat i Word-dokument
linktitle: Horisontellt regelformat i Word-dokument
second_title: Aspose.Words Document Processing API
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

### Vanliga frågor om horisontellt regelformat i word-dokument

#### F: Kan jag använda olika färger på den horisontella regeln?

A: Absolut! Med Aspose.Words för .NET kan du enkelt anpassa färgen på den horisontella regeln genom att ställa in egenskapen Color till önskat färgvärde. Detta gör att du kan matcha den horisontella regeln med ditt dokuments övergripande design.

#### F: Är det möjligt att justera bredden och höjden på den horisontella linjalen?

S: Ja, du har full kontroll över den horisontella linjalens bredd och höjd. Genom att ändra egenskaperna WidthPercent och Height kan du uppnå önskade dimensioner för den horisontella regeln.

#### F: Kan jag ändra justeringen av den horisontella regeln i dokumentet?

A: Visst! Aspose.Words för .NET gör att du kan ange justeringen av den horisontella regeln med hjälp av egenskapen Alignment. Du kan välja mellan olika alternativ som Center, Left, Right och Justified.

#### F: Kan jag använda skuggning eller bakgrundsfärg på den horisontella regeln?

S: Ja, du kan lägga till skuggning eller bakgrundsfärg till den horisontella regeln. Som standard är egenskapen NoShade inställd på true, men du kan ställa in den på false och definiera skuggningen med lämpliga metoder.

#### F: Kan jag infoga flera horisontella regler i ett enda dokument?

A: Absolut! Du kan infoga flera horisontella regler i ett Word-dokument med Aspose.Words för .NET. Upprepa helt enkelt stegen i handledningen efter behov för att lägga till så många horisontella regler som du behöver.