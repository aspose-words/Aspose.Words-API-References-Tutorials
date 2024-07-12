---
title: Zobrazit gramatické a pravopisné chyby
linktitle: Zobrazit gramatické a pravopisné chyby
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce povolit zobrazení gramatických a pravopisných chyb v dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C#, který umožní zobrazení gramatických a pravopisných chyb pomocí Aspose.Words pro .NET. Tato funkce umožňuje zobrazit gramatické a pravopisné chyby v dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument Wordu, u kterého chceme zobrazit gramatické a pravopisné chyby. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Povolte zobrazení chyb

Nyní povolíme zobrazení gramatických a pravopisných chyb v dokumentu. Chcete-li povolit zobrazení chyb, použijte následující kód:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Tento kód umožňuje zobrazení gramatických chyb (`ShowGrammaticalErrors`) a pravopisné chyby (`ShowSpellingErrors`) v dokumentu.

### Příklad zdrojového kódu pro Zobrazit gramatické a pravopisné chyby pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak povolit zobrazení gramatických a pravopisných chyb v dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce v tomto kurzu můžete tuto funkci snadno aktivovat ve svých vlastních dokumentech.