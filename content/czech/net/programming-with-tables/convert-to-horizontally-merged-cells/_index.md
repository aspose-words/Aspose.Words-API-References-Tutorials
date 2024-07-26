---
title: Převést na vodorovně sloučené buňky
linktitle: Převést na vodorovně sloučené buňky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak převést buňky tabulky na vodorovně sloučené buňky v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

tomto tutoriálu se naučíme, jak používat Aspose.Words pro .NET k převodu buněk tabulky na horizontálně sloučené buňky v dokumentu aplikace Word. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově manipulovat s buňkami tabulky v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu a přístup k tabulce
Abychom mohli textový procesor spustit s tabulkou, musíme načíst dokument, který ji obsahuje, a získat k němu přístup. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Přístup k poli
Table table = doc.FirstSection.Body.Tables[0];
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů. Také se ujistěte, že dokument obsahuje tabulku s vodorovně sloučenými buňkami.

## Krok 3: Převeďte na vodorovně sloučené buňky
 Dále převedeme buňky tabulky na vodorovně sloučené buňky pomocí`ConvertToHorizontallyMergedCells()` metoda. Použijte následující kód:

```csharp
// Převést na vodorovně sloučené buňky
table. ConvertToHorizontallyMergedCells();
```

 Zde jen zavoláme`ConvertToHorizontallyMergedCells()` metoda na poli k provedení převodu.

### Ukázkový zdrojový kód pro Převést na horizontálně sloučené buňky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Nyní mají sloučené buňky příslušné příznaky sloučení.
	table.ConvertToHorizontallyMergedCells();
```

## Závěr
tomto tutoriálu jsme se naučili, jak převést buňky tabulky na horizontálně sloučené buňky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově manipulovat s buňkami tabulky v dokumentech aplikace Word. Tato funkce vám umožňuje spravovat a organizovat data flexibilním a personalizovaným způsobem v tabulce.