---
title: Exporteer Cid-URL's voor Mhtml-bronnen
linktitle: Exporteer Cid-URL's voor Mhtml-bronnen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het exporteren van CID-URL's van MHTML-bronnen bij het opslaan van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

In deze zelfstudie leiden we u door de C#-broncode om CID-URL's voor MHTML-bronnen te exporteren met Aspose.Words voor .NET. Met deze functie kunt u CID-URL's van MHTML-bronnen exporteren wanneer u een document in MHTML-indeling opslaat.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het document dat we willen exporteren. Gebruik de volgende code om het document vanuit een opgegeven map te laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Met deze code wordt een exemplaar gemaakt van`Document` door het document uit de opgegeven map te laden.

## Stap 3: HTML-back-upopties configureren

Nu gaan we HTML-opslagopties configureren om CID-URL's van MHTML-bronnen te exporteren. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` met het opslagformaat ingesteld op MHTML. Het maakt ook de export van CID-URL's van MHTML-bronnen mogelijk door in te stellen`ExportCidUrlsForMhtmlResources` naar`true`.

## Stap 4: Het document converteren en opslaan naar MHTML

Ten slotte zullen we het document naar MHTML converteren met behulp van de eerder geconfigureerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Deze code converteert het document naar MHTML en slaat het op in een bestand met de CID-URL's van de geëxporteerde MHTML-bronnen.

### Voorbeeldbroncode voor het exporteren van Cid-URL's voor Mhtml-bronnen met behulp van Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Zorg ervoor dat u het juiste pad naar de documentenmap opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u CID-URL's van MHTML-bronnen kunt exporteren wanneer u een document in MHTML-indeling opslaat met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig CID-URL's in uw geëxporteerde MHTML-documenten beheren.

