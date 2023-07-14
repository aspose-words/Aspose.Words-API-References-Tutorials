---
title: Lägg till japanska som redigeringsspråk
linktitle: Lägg till japanska som redigeringsspråk
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att lägga till japanska som redigeringsspråk med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

den här handledningen tar vi dig steg för steg för att förstå och implementera funktionen för att lägga till japanska som redigeringsspråk med Aspose.Words för .NET. Med den här funktionen kan du ställa in språkinställningar när du laddar ett dokument och lägga till japanska som redigeringsspråk.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som inte innehåller ett standardredigeringsspråk och som vi vill lägga till japanska. Använd följande kod för att ladda dokumentet:

```csharp
LoadOptions loadOptions = new LoadOptions();

// Ställ in de språkinställningar som ska användas när dokumentet laddas.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Steg 3: Kontrollera standardspråket

Efter att ha laddat dokumentet kommer vi att kontrollera om standardredigeringsspråket är korrekt inställt på japanska. Använd följande kod för att få Fjärranösterns språk-ID:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Koden kontrollerar om språk-ID:t för Fjärran Östern matchar japanska. Enligt resultatet visas ett motsvarande meddelande.

### Exempel på källkod för Lägg till japanska som redigeringsspråk med Aspose.Words för .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Ställ in språkinställningar som kommer att användas när dokumentet laddas.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

