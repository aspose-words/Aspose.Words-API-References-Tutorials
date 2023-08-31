---
title: Tillämpa kanter och skuggning på stycke i Word-dokument
linktitle: Tillämpa kanter och skuggning på stycke i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder kanter och skuggning på ett stycke i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
den här handledningen kommer vi att visa dig hur du använder gränser och skuggning på ett stycke i Word-dokument med funktionen i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa formateringsändringar.

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

## Slutsats

 den här handledningen lärde vi oss hur man tillämpar ramar och skuggning på ett stycke i ett Word-dokument med Aspose.Words för .NET. Genom att konfigurera styckets`Borders` och`Shading` egenskaper kunde vi ställa in ramstil, linjefärg och fyllningsfärg för stycket. Aspose.Words för .NET ger kraftfulla formateringsmöjligheter för att anpassa utseendet på stycken och förbättra den visuella representationen av dina dokument.

### FAQ's

#### F: Hur använder jag kanter och skuggning på ett stycke i ett Word-dokument med Aspose.Words för .NET?

S: För att tillämpa ramar och skuggning på ett stycke i ett Word-dokument med Aspose.Words för .NET, följ dessa steg:
1.  Skapa ett nytt dokument och en`DocumentBuilder` objekt.
2.  Konfigurera styckegränserna genom att gå till`Borders` egendom av`ParagraphFormat` och ange kantstilen för varje sida.
3.  Konfigurera styckefyllningen genom att gå till`Shading` egendom av`ParagraphFormat` och specificera textur och fyllningsfärger.
4.  Lägg till innehåll i stycket med hjälp av`Write` metod för`DocumentBuilder`.
5.  Spara dokumentet med hjälp av`Save` metod.

#### F: Hur ställer jag in ramstilen för varje sida av stycket?

 S: För att ställa in ramstilen för varje sida av stycket kan du komma åt`Borders` egendom av`ParagraphFormat` och ställ in`LineStyle` egendom för varje`BorderType` (t.ex,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Du kan ange olika linjestilar som t.ex`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, etc.

#### F: Hur anger jag textur och fyllningsfärger för styckeskuggningen?

 S: För att ange textur och fyllningsfärger för styckeskuggningen kan du komma åt`Shading` egendom av`ParagraphFormat` och ställ in`Texture` egenskap till ett önskat texturindex (t.ex.`TextureIndex.TextureDiagonalCross` ). Du kan också ställa in`BackgroundPatternColor` och`ForegroundPatternColor` egenskaper till önskade färger med hjälp av`System.Drawing.Color` klass.