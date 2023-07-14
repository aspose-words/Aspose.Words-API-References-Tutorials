---
title: Infoga inbyggd bild
linktitle: Infoga inbyggd bild
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
