---
title: Tekstinvoerformulierveld exporteren als tekst
linktitle: Tekstinvoerformulierveld exporteren als tekst
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het exporteren van tekstinvoerformuliervelden als platte tekst met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

In deze zelfstudie leiden we u door de C#-broncode om tekstinvoerformuliervelden als platte tekst te exporteren met Aspose.Words voor .NET. Met deze functie kunt u tekstinvoerformuliervelden exporteren als leesbare tekst, in plaats van ze te exporteren als HTML-invoerelementen.

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

Nu zullen we de HTML-opslagopties configureren om tekstinvoerformuliervelden als platte tekst te exporteren. Gebruik de volgende code:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// De opgegeven map moet bestaan en leeg zijn.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` en stelt de`ExportTextInputFormFieldAsText` optie om`true` om tekstinvoerformuliervelden als platte tekst te exporteren. Bovendien specificeert het de map waarin de uitgepakte afbeeldingen zullen worden opgeslagen.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder geconfigureerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Deze code converteert het document naar HTML door tekstinvoerformuliervelden als platte tekst te exporteren, en slaat het geëxporteerde HTML-bestand op in de opgegeven map.

### Voorbeeldbroncode voor het exporteren van tekstinvoerformulierveld als tekst met Aspose.Words voor .NET


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// De opgegeven map moet bestaan en moet leeg zijn.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Stel een optie in om formuliervelden te exporteren als platte tekst, niet als HTML-invoerelementen.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Zorg ervoor dat u het juiste pad naar de documentenmap opgeeft in het`dataDir` variabel.