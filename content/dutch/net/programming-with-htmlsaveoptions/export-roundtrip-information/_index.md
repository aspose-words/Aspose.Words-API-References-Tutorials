---
title: Retourinformatie exporteren
linktitle: Retourinformatie exporteren
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het exporteren van retourinformatie bij het opslaan van een document als HTML met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

In deze zelfstudie leiden we u door de C#-broncode om roundtrip-informatie uit een document te exporteren met Aspose.Words voor .NET. Met deze functie kunt u roundtrip-informatie opnemen in het geëxporteerde HTML-bestand, waardoor het gemakkelijker wordt om wijzigingen op te halen die in het originele document zijn aangebracht.

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

Nu gaan we de HTML-opslagopties configureren om de retourinformatie van het document te exporteren. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions`en stelt de`ExportRoundtripInformation` optie om`true` om retourinformatie op te nemen bij het exporteren.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder geconfigureerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Deze code converteert het document naar HTML, inclusief de roundtrip-informatie, en slaat het geëxporteerde HTML-bestand op in de opgegeven map.

### Voorbeeldbroncode voor het exporteren van roundtrip-informatie met Aspose.Words voor .NET


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Zorg ervoor dat u het juiste pad naar de documentenmap opgeeft in het`dataDir` variabel.