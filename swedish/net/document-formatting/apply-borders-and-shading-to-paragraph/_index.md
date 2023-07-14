---
title: Applicera kanter och skuggning på stycke
linktitle: Applicera kanter och skuggning på stycke
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder kanter och skuggning på ett stycke med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

I den här handledningen kommer vi att visa dig hur du använder kanter och skuggning på ett stycke med funktionen i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa formateringsändringar.

## Steg 1: Skapa och konfigurera dokumentet

Börja med att skapa ett nytt dokument och ett tillhörande DocumentBuilder-objekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Kantkonfiguration

Låt oss nu konfigurera styckekanterna genom att ange kantstilen för varje sida. Här är hur:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Steg 3: Infill Setup

Vi kommer nu att konfigurera styckefyllningen genom att ange texturen och fyllningsfärgerna. Här är hur:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Steg 4: Lägg till innehåll

Vi kommer att lägga till lite formaterat innehåll till stycket. Här är hur:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Exempel på källkod för Apply Borders And Shading To Paragraph med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Apply Borders and shading to Paragraph med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```
