---
title: Converteer metabestanden naar SVG
linktitle: Converteer metabestanden naar SVG
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het converteren van metabestanden naar SVG-indeling bij het converteren van een document naar HTML met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

In deze zelfstudie leiden we u door de C#-broncode om metabestanden naar SVG-indeling te converteren met Aspose.Words voor .NET. Met deze functie kunt u metabestanden naar SVG-indeling converteren wanneer u een document naar HTML converteert.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Een SVG-afbeelding in het document invoegen

In deze stap voegen we een SVG-afbeelding in het te converteren document in. Gebruik de volgende code om een SVG-afbeelding in te voegen met behulp van een HTML-tag:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Met deze code wordt een exemplaar gemaakt van`Document` En`DocumentBuilder` om het document op te bouwen. Het voegt een`<svg>` label met daarin een`<polygon>` element met attributen om de vorm en stijl van de SVG-afbeelding te definiëren.

## Stap 3: Stel HTML-opslagopties in

Nu gaan we de HTML-opslagopties instellen, waarbij we specificeren dat metabestanden moeten worden geconverteerd naar SVG-indeling. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` en sets`MetafileFormat` naar`HtmlMetafileFormat.Svg` om te specificeren dat metabestanden moeten worden geconverteerd naar SVG-indeling bij conversie naar HTML.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder gedefinieerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Deze code converteert het document naar HTML en slaat het op in een bestand, waarbij de metabestanden worden geconverteerd naar SVG.

### Voorbeeldbroncode voor het converteren van metabestanden naar SVG met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
