---
title: Voeg het voorvoegsel van de CSS-klassenaam toe
linktitle: Voeg het voorvoegsel van de CSS-klassenaam toe
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het toevoegen van een CSS-klassenaamvoorvoegsel bij het converteren van een document naar HTML met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

In deze zelfstudie leiden we u door de C#-broncode om een CSS-klassenaamvoorvoegsel toe te voegen met Aspose.Words voor .NET. Met deze functie kunt u een aangepast voorvoegsel toevoegen aan gegenereerde CSS-klassenamen wanneer u een document naar HTML converteert.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document dat we naar HTML willen converteren. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Stel HTML-opslagopties in

Laten we nu de HTML-opslagopties instellen, inclusief het CSS-stylesheettype en het CSS-klassenaamvoorvoegsel. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` en sets`CssStyleSheetType` naar`CssStyleSheetType.External`om een extern CSS-stijlblad te genereren, en`CssClassNamePrefix` naar`"pfx_"` naar voorvoegsel`"pfx_"` om de CSS-klasse te benoemen.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder gedefinieerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Deze code converteert het document naar HTML en slaat het op in een bestand waaraan het CSS-klassenaamvoorvoegsel is toegevoegd.

### Voorbeeldbroncode voor het toevoegen van een CSS-klassenaamvoorvoegsel met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u een CSS-klassenaamvoorvoegsel kunt toevoegen bij het converteren van een document naar HTML met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u de CSS-klassenamen in uw geconverteerde HTML-documenten aanpassen.