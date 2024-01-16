---
title: Nastavit ruštinu jako výchozí jazyk úprav
linktitle: Nastavit ruštinu jako výchozí jazyk úprav
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením ruštiny jako výchozího jazyka pro úpravy dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro nastavení ruštiny jako výchozího jazyka pro úpravy pomocí Aspose.Words pro .NET. Tato funkce umožňuje nastavit výchozí jazyk při načítání dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument Wordu, pro který chceme nastavit ruštinu jako výchozí jazyk úprav. K načtení dokumentu použijte následující kód:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Kontrola výchozího jazyka

Po nahrání dokumentu zkontrolujeme, zda byl jako výchozí jazyk správně nastaven ruština. K získání výchozího ID jazyka použijte následující kód:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Kód kontroluje, zda ID jazyka odpovídá ruštině. Podle výsledku zobrazí odpovídající zprávu.

### Příklad zdrojového kódu pro Nastavit ruštinu jako výchozí jazyk pro úpravy pomocí Aspose.Words pro .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak nastavit ruštinu jako výchozí jazyk pro úpravy dokumentu pomocí Aspose.Words pro .NET. Postupujte podle návodu