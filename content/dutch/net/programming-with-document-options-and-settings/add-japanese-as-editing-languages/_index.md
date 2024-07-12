---
title: Voeg Japans toe als bewerkingstalen
linktitle: Voeg Japans toe als bewerkingstalen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om Japans als bewerkingstaal toe te voegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

In deze zelfstudie nemen we u stap voor stap mee om de functionaliteit van het toevoegen van Japans als bewerkingstaal met Aspose.Words voor .NET te begrijpen en te implementeren. Met deze functie kunt u taalvoorkeuren instellen bij het laden van een document en Japans toevoegen als bewerkingstaal.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document dat geen standaard bewerkingstaal bevat en waaraan we Japans willen toevoegen. Gebruik de volgende code om het document te laden:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Stel de taalvoorkeuren in die worden gebruikt bij het laden van het document.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Stap 3: De standaardtaal controleren

Na het laden van het document controleren we of de standaard bewerkingstaal correct is ingesteld op Japans. Gebruik de volgende code om de taal-ID van het Verre Oosten op te halen:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

De code controleert of de taal-ID van het Verre Oosten overeenkomt met die van het Japans. Afhankelijk van het resultaat wordt een bijbehorend bericht weergegeven.

### Voorbeeldbroncode voor het toevoegen van Japans als bewerkingstalen met Aspose.Words voor .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Stel de taalvoorkeuren in die worden gebruikt wanneer het document wordt geladen.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

