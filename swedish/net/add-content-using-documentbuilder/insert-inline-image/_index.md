---
title: Infoga inline bild i Word-dokument
linktitle: Infoga inline bild i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar inline-bilder i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-inline-image/
---
I den här omfattande handledningen kommer du att lära dig hur du infogar inline-bilder i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna lägga till bilder direkt i texten i dina dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga en inbyggd bild
Använd sedan metoden InsertImage i klassen DocumentBuilder för att infoga en inline-bild i dokumentet. Ange sökvägen till bildfilen som en parameter:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Steg 3: Spara dokumentet
När du har infogat den infogade bilden sparar du dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Exempel på källkod för Infoga inbyggd bild med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga en inline-bild med Aspose.Words för .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du infogar inline-bilder i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu lägga till bilder sömlöst i texten i dina dokument.

Inline-bilder är användbara för olika scenarier, som att lägga till illustrationer, logotyper eller andra visuella element direkt i dokumentflödet.

### Vanliga frågor för att infoga inline bild i word-dokument

#### F: Kan jag ändra storlek på inlinebilderna i Word-dokumentet?

S: Ja, du kan ändra storlek på inline-bilderna med Aspose.Words för .NET. När du har infogat bilden kan du manipulera dess storlek genom att justera egenskaperna för bredd och höjd för Shape-objektet som representerar bilden.

#### F: Är det möjligt att lägga till alt-text till inline-bilder för tillgänglighetssyften?

S: Ja, du kan lägga till alt-text till inline-bilder för att förbättra tillgängligheten. Aspose.Words för .NET stöder tillägg av alt-text till bilder, vilket gör att skärmläsare och andra hjälpmedel kan beskriva bildinnehållet för synskadade användare.

#### F: Kan jag använda formatering eller stilar på inline-bilderna?

A: Absolut! Aspose.Words för .NET tillhandahåller omfattande formateringsalternativ för inline-bilder. Du kan använda olika stilar, ramar, effekter och andra formateringsattribut på bilderna för att matcha dokumentets visuella design.

#### F: Har Aspose.Words för .NET stöd för att infoga bilder från en ström eller byte-array?

S: Ja, du kan infoga inline-bilder från strömmar eller byte-arrayer med Aspose.Words för .NET. Detta gör att du kan arbeta med bilder som laddats från externa källor eller dynamiskt genererade bilder.

#### F: Kan jag infoga bilder på specifika positioner i textinnehållet?

S: Ja, klassen DocumentBuilder i Aspose.Words för .NET ger exakt kontroll över infogningspositionen för inline-bilder. Du kan ange den exakta platsen i texten där bilden ska infogas.