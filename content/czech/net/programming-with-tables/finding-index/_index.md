---
title: Index hledání
linktitle: Index hledání
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak najít indexy tabulek, řádků a buněk v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/finding-index/
---

V tomto tutoriálu se naučíme, jak používat Aspose.Words pro .NET k nalezení indexů tabulky, řádku a buňky v dokumentu aplikace Word. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově najít indexy prvků pole v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu a přístup k tabulce
Abychom mohli textový procesor spustit s tabulkou, musíme načíst dokument, který ji obsahuje, a získat k němu přístup. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Tables.docx");

// Přístup k poli
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Najděte tabulku, řádek a index buněk
Dále najdeme indexy tabulky, řádků a buněk v poli pomocí metod poskytovaných Aspose.Words pro .NET. Použijte následující kód:

```csharp
// Najděte index tabulky
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
int tableIndex = allTables.IndexOf(table);
Console.WriteLine("\nTable index is " + tableIndex);

// Najděte index řádku
int rowIndex = table.IndexOf(table.LastRow);
Console.WriteLine("\nLine index is " + rowIndex);

// Najděte index buňky
Row row = table. LastRow;
int cellIndex = row.IndexOf(row.Cells[4]);
Console.WriteLine("\nCell index is " + cellIndex);
```

 Zde používáme`GetChildNodes` způsob, jak získat všechny tabulky v dokumentu. Pak použijeme`IndexOf` najít index konkrétní tabulky v kolekci všech tabulek. Podobně používáme i my`IndexOf` najít index posledního řádku v tabulce a`IndexOf` uvnitř řádku, abyste našli index konkrétní buňky.

### Ukázka zdrojového kódu pro hledání indexu pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
	int tableIndex = allTables.IndexOf(table);
	Console.WriteLine("\nTable index is " + tableIndex);
	int rowIndex = table.IndexOf(table.LastRow);
	Console.WriteLine("\nRow index is " + rowIndex);
	Row row = table.LastRow;
	int cellIndex = row.IndexOf(row.Cells[4]);
	Console.WriteLine("\nCell index is " + cellIndex);
```

## Závěr
tomto tutoriálu jsme se naučili, jak najít indexy tabulky, řádku a buňky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově najít a identifikovat přesné pozice prvků pole v dokumentech aplikace Word. Tato funkce vám umožňuje přesně manipulovat a interagovat s prvky pole tak, aby vyhovovaly vašim specifickým potřebám.