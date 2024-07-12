---
title: Ställ in ryska som standardredigeringsspråk
linktitle: Ställ in ryska som standardredigeringsspråk
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ställa in ryska som standardredigeringsspråk för ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

den här handledningen går vi igenom C#-källkoden för att ställa in ryska som standardredigeringsspråk med Aspose.Words för .NET. Den här funktionen låter dig ställa in standardspråket när du laddar ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet för vilket vi vill ställa in ryska som standardspråk för redigering. Använd följande kod för att ladda dokumentet:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Kontrollera standardspråket

Efter att ha laddat upp dokumentet kommer vi att kontrollera om standardspråket är korrekt inställt på ryska. Använd följande kod för att få standardspråk-ID:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Koden kontrollerar om språk-ID stämmer överens med ryska. Enligt resultatet visas ett motsvarande meddelande.

### Exempel på källkod för Ange ryska som standardredigeringsspråk med Aspose.Words för .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du ställer in ryska som standardredigeringsspråk för ett dokument med Aspose.Words för .NET. Genom att följa stegguiden