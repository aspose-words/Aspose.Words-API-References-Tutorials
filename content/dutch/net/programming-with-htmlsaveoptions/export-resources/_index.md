---
title: Hulpbronnen exporteren
linktitle: Hulpbronnen exporteren
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het exporteren van documentbronnen bij het opslaan als HTML met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/export-resources/
---

In deze zelfstudie leiden we u door de C#-broncode om documentbronnen te exporteren met Aspose.Words voor .NET. Met deze functie kunt u bronnen, zoals lettertypen, exporteren als externe bestanden wanneer u een document in HTML-indeling opslaat.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het document dat we willen exporteren. Gebruik de volgende code om het document vanuit een opgegeven map te laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Met deze code wordt een exemplaar gemaakt van`Document` door het document uit de opgegeven map te laden.

## Stap 3: HTML-back-upopties configureren

Nu zullen we de HTML-opslagopties configureren om de documentbronnen te exporteren. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://voorbeeld.com/resources"
};
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` en stelt de volgende opties in:

- `CssStyleSheetType` ingesteld op`CssStyleSheetType.External` om het CSS-stijlblad naar een extern bestand te exporteren.
- `ExportFontResources` ingesteld op`true` om lettertypebronnen te exporteren.
- `ResourceFolder` specificeert de doelmap waar de bronnen worden opgeslagen.
- `ResourceFolderAlias`specificeert de URL-alias die wordt gebruikt om toegang te krijgen tot bronnen.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder geconfigureerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Deze code converteert het document naar HTML en slaat de bronnen op in de opgegeven map, met behulp van de opgegeven URL-alias.

### Voorbeeldbroncode voor het exporteren van bronnen met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://voorbeeld.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Zorg ervoor dat u het juiste pad naar de documentenmap opgeeft in het`dataDir` variabel.