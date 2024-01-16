---
title: Lettertypen exporteren als basis 64
linktitle: Lettertypen exporteren als basis 64
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het exporteren van basis 64-lettertypen bij het opslaan van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

In deze zelfstudie leiden we u door de C#-broncode om basis 64-lettertypen te exporteren met Aspose.Words voor .NET. Met deze functie kunt u lettertypen exporteren als basisgegevens wanneer u een document in HTML-indeling opslaat.

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

Nu zullen we de HTML-opslagopties configureren om basis 64-lettertypen te exporteren. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` en sets`ExportFontsAsBase64` naar`true` om te specificeren dat lettertypen moeten worden geëxporteerd als basis 64-gegevens bij het opslaan als HTML.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder geconfigureerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Deze code converteert het document naar HTML en slaat het op in een bestand, waarbij de lettertypen worden geëxporteerd als basisgegevens.

### Voorbeeldbroncode voor het exporteren van lettertypen als basis 64 met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Zorg ervoor dat u het juiste pad naar de documentenmap opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u basis 64-lettertypen kunt exporteren wanneer u een document als HTML opslaat met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u lettertypen eenvoudig veilig exporteren en insluiten in uw HTML-documenten.