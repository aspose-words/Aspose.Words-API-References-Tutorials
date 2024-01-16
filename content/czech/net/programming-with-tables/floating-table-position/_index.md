---
title: Pozice plovoucího stolu
linktitle: Pozice plovoucího stolu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak umístit tabulku do plovoucí pozice v dokumentu aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/floating-table-position/
---

V tomto tutoriálu se naučíme, jak používat Aspose.Words pro .NET k umístění tabulky do plovoucí pozice v dokumentu aplikace Word. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově ovládat polohu a zarovnání plovoucích tabulek v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu a přístup k tabulce
Abychom mohli textový procesor spustit s tabulkou, musíme načíst dokument, který ji obsahuje, a získat k němu přístup. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Přístup k poli
Table table = doc.FirstSection.Body.Tables[0];
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů. Také se ujistěte, že dokument obsahuje tabulku, která bude umístěna v plovoucí poloze.

## Krok 3: Umístění plovoucí desky
Dále umístíme tabulku do plovoucí pozice pomocí vlastností poskytovaných Aspose.Words pro .NET. Použijte následující kód:

```csharp
// Umístění plovoucího stolu
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Zde používáme`AbsoluteHorizontalDistance` vlastnost pro nastavení absolutní vodorovné vzdálenosti tabulky od levého okraje stránky. Používáme také`RelativeVerticalAlignment` vlastnost pro nastavení relativního vertikálního zarovnání tabulky k okolnímu obsahu.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s tabulkou umístěnou v plovoucí poloze. Použijte následující kód:

```csharp
// Uložte upravený dokument
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro pozici plovoucí tabulky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak umístit tabulku do plovoucí pozice v dokumentu aplikace Word pomocí Aspose.Words for .NET. Dodržováním tohoto podrobného průvodce a implementací poskytnutého kódu C# můžete programově řídit pozici a zarovnání plovoucích tabulek v dokumentech aplikace Word.