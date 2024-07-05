---
title: Nastavení stránky dokumentu
linktitle: Nastavení stránky dokumentu
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením rozvržení dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/document-page-setup/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro konfiguraci rozvržení dokumentu pomocí Aspose.Words pro .NET. Tato funkce umožňuje nastavit režim rozvržení, počet znaků na řádek a počet řádků na stránku.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument aplikace Word, který chceme nakonfigurovat. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Nastavení rozvržení

Nyní nakonfigurujeme rozvržení dokumentu. Pomocí následujícího kódu nastavte režim rozvržení, počet znaků na řádek a počet řádků na stránku:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Tento kód nastaví režim rozvržení na "Mřížka" a poté určuje počet znaků na řádek a počet řádků na stránku.

### Příklad zdrojového kódu pro nastavení stránky dokumentu pomocí Aspose.Words pro .NET


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Nastavte režim rozvržení pro sekci umožňující definovat chování mřížky dokumentu.
	// Všimněte si, že karta Mřížka dokumentu se zobrazí v dialogovém okně Vzhled stránky aplikace MS Word
	// pokud je jako jazyk úprav definován nějaký asijský jazyk.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak nakonfigurovat rozvržení dokumentu pomocí Aspose.Words pro .NET. Podle podrobného průvodce uvedeného v tomto kurzu můžete snadno přizpůsobit rozvržení svých vlastních dokumentů.