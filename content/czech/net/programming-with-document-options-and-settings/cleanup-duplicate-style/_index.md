---
title: Vyčištění duplicitního stylu
linktitle: Vyčištění duplicitního stylu
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem k vyčištění duplicitních stylů v dokumentu pomocí Aspose.Words for .NET. Plný zdrojový kód v ceně.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

V tomto tutoriálu vás krok za krokem provedeme zdrojovým kódem C# k vyčištění duplicitních stylů pomocí Aspose.Words pro .NET. Tato funkce pomáhá odstranit duplicitní styly z dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument aplikace Word, který chceme vyčistit. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Před čištěním spočítejte styly

Než přistoupíme k čištění, spočítáme počet stylů přítomných v dokumentu. K zobrazení počtu stylů použijte následující kód:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Tento příkaz zobrazuje počet stylů přítomných v dokumentu.

## Krok 4: Vyčistěte duplicitní styly

Nyní vyčistíme duplicitní styly z dokumentu. K provedení čištění použijte následující kód:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Tento kód vyčistí duplicitní styly z dokumentu pomocí zadaných možností. V tomto příkladu jsme povolili`DuplicateStyle` možnost vyčistit duplicitní styly.

## Krok 5: Po vyčištění počítejte styly

Po provedení čištění znovu spočítáme počet stylů, abychom zkontrolovali, zda se snížil. K zobrazení počtu nových stylů použijte následující kód:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Tento příkaz zobrazuje počet stylů zbývajících po vyčištění.

### Příklad zdrojového kódu pro Cleanup Duplicate Style pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Počet stylů před vyčištěním.
	Console.WriteLine(doc.Styles.Count);

	// Vyčistí duplicitní styly z dokumentu.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//Počet stylů po vyčištění byl snížen.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```