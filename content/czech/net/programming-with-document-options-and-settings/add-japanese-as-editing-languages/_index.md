---
title: Přidat japonštinu jako jazyky pro úpravy
linktitle: Přidat japonštinu jako jazyky pro úpravy
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce přidáním japonštiny jako jazyka pro úpravy pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

V tomto tutoriálu vás krok za krokem provedeme, abyste pochopili a implementovali funkce přidání japonštiny jako jazyka pro úpravy pomocí Aspose.Words pro .NET. Tato funkce umožňuje nastavit jazykové preference při načítání dokumentu a přidat japonštinu jako jazyk úprav.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument aplikace Word, který neobsahuje výchozí jazyk úprav a do kterého chceme přidat japonštinu. K načtení dokumentu použijte následující kód:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Nastavte jazykové preference, které budou použity při načítání dokumentu.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Krok 3: Kontrola výchozího jazyka

Po načtení dokumentu zkontrolujeme, zda byl správně nastaven výchozí jazyk úprav na japonštinu. K získání ID jazyka Dálného východu použijte následující kód:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Kód zkontroluje, zda ID jazyka Dálného východu odpovídá japonštině. Podle výsledku zobrazí odpovídající zprávu.

### Příklad zdrojového kódu pro Přidat japonštinu jako editační jazyky pomocí Aspose.Words pro .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Nastavte jazykové preference, které budou použity při načítání dokumentu.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

