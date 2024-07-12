---
title: Converteer metabestanden naar Emf of Wmf
linktitle: Converteer metabestanden naar Emf of Wmf
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het converteren van metabestanden naar EMF- of WMF-formaten bij het converteren van een document naar HTML met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

In deze zelfstudie leiden we u door de C#-broncode om metabestanden naar EMF- of WMF-indeling te converteren met Aspose.Words voor .NET. Met deze functie kunt u afbeeldingen in metabestandsindeling converteren naar meer compatibele indelingen zoals EMF of WMF wanneer u een document naar HTML converteert.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Een afbeelding in het document invoegen

In deze stap voegen we een afbeelding in het te converteren document in. Gebruik de volgende code om een afbeelding uit een gegevensbron in te voegen met behulp van een HTML-tag:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Met deze code wordt een exemplaar gemaakt van`Document`En`DocumentBuilder` om het document op te bouwen. Het voegt een`<img>` tag in het document met een base64-gecodeerde afbeelding.

## Stap 3: Stel HTML-opslagopties in

Nu gaan we de HTML-opslagopties instellen, inclusief het metabestandsformaat dat voor afbeeldingen moet worden gebruikt. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` en sets`MetafileFormat` naar`HtmlMetafileFormat.EmfOrWmf` om te specificeren dat metabestanden moeten worden geconverteerd naar EMF- of WMF-indeling bij conversie naar HTML.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder gedefinieerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Deze code converteert het document naar HTML en slaat het op in een bestand met de geconverteerde metabestanden in EMF- of WMF-indeling, afhankelijk van de ingestelde opslagopties.

### Voorbeeldbroncode voor het converteren van metabestanden naar Emf of Wmf met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Zorg ervoor dat u het juiste pad naar de documentenmap opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u metabestanden naar EMF- of WMF-indelingen converteert wanneer u een document naar HTML converteert met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig metabestanden in uw geconverteerde HTML-documenten beheren.