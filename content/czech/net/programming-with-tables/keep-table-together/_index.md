---
title: Udržujte stůl pohromadě
linktitle: Udržujte stůl pohromadě
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak udržet stůl pohromadě v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/keep-table-together/
---

V tomto tutoriálu se naučíme, jak držet stůl pohromadě v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto tutoriálu budete schopni udržet tabulku neporušenou, aniž by se rozdělovala na více stránek v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu a načtení tabulky
Chcete-li spustit textový procesor s tabulkou, musíme načíst dokument a načíst tabulku, kterou chceme zachovat pohromadě. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Získejte tabulku
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Povolte možnost „KeepWithNext“.
Aby tabulka zůstala pohromadě a zabránila jejímu rozdělení na více stránek, musíme pro každý odstavec v tabulce kromě posledních odstavců posledního řádku tabulky povolit možnost „KeepWithNext“. Použijte následující kód:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Zde procházíme každou buňku v tabulce a povolíme volbu "KeepWithNext" pro každý odstavec v buňce kromě posledních odstavců posledního řádku v tabulce.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s tabulkou pohromadě. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro Keep Table Together pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Musíme povolit KeepWithNext pro každý odstavec v tabulce, aby se nerozbil přes stránku,
	//kromě posledních odstavců v posledním řádku tabulky.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak držet stůl pohromadě v dokumentu aplikace Word pomocí Aspose.Words for .NET. Dodržováním tohoto podrobného průvodce a implementací poskytnutého kódu C# můžete udržet tabulku nedotčenou a zabránit jejímu rozdělení na více stránek ve vašich dokumentech. Tato funkce vám dává větší kontrolu nad vzhledem a rozložením tabulek v dokumentech.