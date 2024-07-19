---
title: Lettertypenamen oplossen
linktitle: Lettertypenamen oplossen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om ontbrekende lettertypenamen op te lossen bij het converteren naar HTML met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/resolve-font-names/
---

In deze zelfstudie leiden we u door de C#-broncode om ontbrekende lettertypenamen op te lossen met Aspose.Words voor .NET. Met deze functie kunt u ontbrekende lettertypenamen automatisch oplossen bij het converteren van een document naar HTML.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het te verwerken document. Gebruik de volgende code om het document vanuit een opgegeven map te laden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Met deze code wordt een exemplaar gemaakt van`Document` door het document uit de opgegeven map te laden.

## Stap 3: HTML-back-upopties configureren

Nu gaan we HTML-opslagopties configureren om ontbrekende lettertypenamen tijdens de conversie op te lossen. Gebruik de volgende code:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Met deze code wordt een exemplaar gemaakt van`HtmlSaveOptions` en stelt de`ResolveFontNames` optie om`true`om ontbrekende lettertypenamen op te lossen bij het converteren naar HTML. Ook de`PrettyFormat` optie is ingesteld`true` om mooi opgemaakte HTML-code te krijgen.

## Stap 4: Het document converteren en opslaan naar HTML

Ten slotte zullen we het document naar HTML converteren met behulp van de eerder geconfigureerde HTML-opslagopties. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Deze code converteert het document naar HTML door automatisch ontbrekende lettertypenamen om te zetten, en slaat het geconverteerde HTML-bestand op in de opgegeven map.

### Voorbeeldbroncode voor het oplossen van lettertypenamen met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Zorg ervoor dat u het juiste pad naar de documentenmap opgeeft in het`dataDir` variabel.