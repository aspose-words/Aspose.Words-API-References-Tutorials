---
title: Vyčištění nepoužívaných stylů a seznamů
linktitle: Vyčištění nepoužívaných stylů a seznamů
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce čištěním nepoužívaných stylů a seznamů v dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# k vyčištění nepoužívaných stylů a seznamů pomocí Aspose.Words pro .NET. Tato funkce umožňuje odstranit styly a seznamy, které nejsou v dokumentu použity.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument aplikace Word obsahující nepoužívané styly a seznamy, které chceme vyčistit. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Před čištěním spočítejte styly a seznamy

Před čištěním spočítáme počet stylů a seznamů přítomných v dokumentu. K zobrazení počítadel použijte následující kód:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Tyto pokyny ukazují počet stylů a seznamů přítomných v dokumentu před čištěním.

## Krok 4: Vyčistěte nepoužívané styly a seznamy

Nyní z dokumentu vyčistíme nepoužívané styly a seznamy. K provedení čištění použijte následující kód:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Tento kód vyčistí nepoužívané styly a seznamy z dokumentu pomocí zadaných možností. V tomto příkladu jsme povolili`UnusedStyles` možnost odstranit nepoužívané styly a deaktivovat`UnusedLists` možnost zachovat seznamy, i když nejsou používány.

## Krok 5: Po vyčištění spočítejte styly a seznamy

Po provedení vyčištění znovu spočítáme styly a seznamy, abychom zkontrolovali, zda nebyly sbaleny. K zobrazení nových čítačů použijte následující kód:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Tyto pokyny ukazují počty stylů a seznamů zbývajících po čištění.

### Příklad zdrojového kódu pro Cleanup Unused Styles And Lists pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// V kombinaci s vestavěnými styly má nyní dokument osm stylů.
	// Vlastní styl je označen jako „použitý“, pokud je v dokumentu jakýkoli text
	// naformátované v tomto stylu. To znamená, že 4 styly, které jsme přidali, jsou momentálně nepoužívané.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Vyčistí nepoužívané styly a seznamy z dokumentu v závislosti na daných možnostech CleanupOptions.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak vyčistit nepoužívané styly a seznamy z dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce uvedeného v tomto kurzu můžete tuto funkci snadno použít na své vlastní dokumenty.

