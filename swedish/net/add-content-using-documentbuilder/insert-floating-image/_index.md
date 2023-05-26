---
title: Infoga flytande bild
linktitle: Infoga flytande bild
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar flytande bilder i Word-dokument med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-floating-image/
---

I det här omfattande exemplet kommer du att lära dig hur du infogar en flytande bild i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna lägga till bilder med anpassningsbara positionerings- och omslagsalternativ till dina dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga en flytande bild
Använd sedan metoden InsertImage i klassen DocumentBuilder för att infoga en flytande bild. Ange bildfilens sökväg, relativ horisontell och vertikal position, bredd, höjd och radbrytningsalternativ som parametrar:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Steg 3: Spara dokumentet
När du har infogat den flytande bilden, spara dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Exempel på källkod för Infoga flytande bild med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga en flytande bild med Aspose.Words för .NET:
Flytande bilder är användbara för olika scenarier, som att lägga till logotyper, illustrationer eller dekorativa element som kan placeras oberoende av dokumentets text.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertImage(ImagesDir + "Transparent background logo.png",
		RelativeHorizontalPosition.Margin,
		100,
		RelativeVerticalPosition.Margin,
		100,
		200,
		100,
		WrapType.Square);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
	
```

Kom ihåg att justera koden enligt dina specifika krav, inklusive sökvägen till bildfilen och önskade placerings- och omslagsalternativ.

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man infogar en flytande bild i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu förbättra dina dokument med visuellt tilltalande och anpassningsbara flytande bilder.

