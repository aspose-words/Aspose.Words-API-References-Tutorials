---
title: Kombinovat řádky
linktitle: Kombinovat řádky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak kombinovat řádky tabulky v dokumentu aplikace Word s Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/combine-rows/
---

tomto tutoriálu se naučíme, jak používat Aspose.Words pro .NET ke kombinování řádků tabulek v dokumentu aplikace Word. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově manipulovat a slučovat řádky tabulky v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu a přístup k tabulkám
Chcete-li spustit textový procesor s tabulkami, musíme načíst dokument, který je obsahuje, a získat k nim přístup. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Tables.docx");

// Přístup ke stolům
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Kombinace řádků tabulky
Dále spojíme řádky druhé tabulky na konec první tabulky. Použijte následující kód:

```csharp
// Kombinace řádků tabulky
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Zde používáme a`while` smyčky pro iteraci přes všechny řádky druhého pole a přidání na konec prvního pole pomocí`Add` metoda. Dále odstraníme druhou tabulku z dokumentu pomocí`Remove` metoda.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme uložit upravený dokument s kombinovanými řádky tabulky. Použijte následující kód:

```csharp
// Uložte upravený dokument
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázka zdrojového kódu pro Combine Rows pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Řádky z druhé tabulky budou připojeny na konec první tabulky.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Připojte všechny řádky z aktuální tabulky k dalším tabulkám
	// s různým počtem a šířkou buněk lze spojit do jedné tabulky.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak kombinovat řádky tabulek v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově manipulovat s řádky tabulky v dokumentech aplikace Word. Tato funkce umožňuje efektivně sloučit a uspořádat data do tabulky.