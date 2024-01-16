---
title: Stel Russisch in als standaard bewerkingstaal
linktitle: Stel Russisch in als standaard bewerkingstaal
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om Russisch in te stellen als de standaard bewerkingstaal van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

In deze zelfstudie leiden we u door de C#-broncode om Russisch in te stellen als de standaard bewerkingstaal met Aspose.Words voor .NET. Met deze functie kunt u de standaardtaal instellen bij het laden van een document.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document waarvoor we Russisch als standaard bewerkingstaal willen instellen. Gebruik de volgende code om het document te laden:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: De standaardtaal controleren

Na het uploaden van het document controleren wij of de standaardtaal correct is ingesteld op Russisch. Gebruik de volgende code om de standaardtaal-ID op te halen:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

De code controleert of de taal-ID overeenkomt met die van het Russisch. Afhankelijk van het resultaat wordt een bijbehorend bericht weergegeven.

### Voorbeeldbroncode voor het instellen van Russisch als standaardbewerkingstaal met Aspose.Words voor .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u Russisch kunt instellen als de standaardbewerkingstaal voor een document met Aspose.Words voor .NET. Door de stappengids te volgen