---
title: Klonovat kompletní tabulku
linktitle: Klonovat kompletní tabulku
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak naklonovat celou tabulku do dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/clone-complete-table/
---

V tomto tutoriálu se naučíme, jak používat Aspose.Words pro .NET ke klonování celé tabulky do dokumentu aplikace Word. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově klonovat tabulky do dokumentů aplikace Word.

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

## Krok 3: Klonování celého pole
Dále naklonujeme celou tabulku a vložíme ji do dokumentu za originál. Použijte následující kód:

```csharp
// Klonujte pole
Table tableClone = (Table)table.Clone(true);

// Vložte klonovanou tabulku do dokumentu za originál
table.ParentNode.InsertAfter(tableClone, table);

// Mezi dvě tabulky vložte prázdný odstavec
// Jinak budou při uložení sloučeny do jednoho (je to kvůli ověření dokumentu)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Zde používáme`Clone` metoda k vytvoření úplné kopie pole. Poté použijeme`InsertAfter` pro vložení klonované tabulky do dokumentu za původní tabulku. Mezi dvě tabulky také přidáme prázdný odstavec, abychom zabránili jejich sloučení při ukládání.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s naklonovanou tabulkou. Použijte následující kód:

```csharp
// Uložte upravený dokument
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.
  
### Ukázka zdrojového kódu pro Clone Complete Table pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Naklonujte tabulku a vložte ji do dokumentu za originál.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Vložte prázdný odstavec mezi dvě tabulky,
	// jinak budou po uložení spojeny do jednoho, což souvisí s ověřením dokumentu.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak naklonovat celou tabulku do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově klonovat tabulky v dokumentech aplikace Word. Tato funkce vám umožňuje provádět pokročilé manipulace s poli tak, aby vyhovovaly vašim specifickým potřebám.