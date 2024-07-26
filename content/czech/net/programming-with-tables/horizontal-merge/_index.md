---
title: Horizontální sloučení
linktitle: Horizontální sloučení
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak horizontálně sloučit buňky v tabulce aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/horizontal-merge/
---

V tomto tutoriálu se naučíme, jak horizontálně sloučit buňky v tabulce v dokumentu Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově sloučit buňky v tabulkách aplikace Word vodorovně.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu a inicializace generátoru dokumentů
Chcete-li spustit Textový procesor s tabulkou a buňkami, musíme vytvořit nový dokument a inicializovat generátor dokumentů. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Vytvořte dokument a inicializujte generátor dokumentů
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Sestavení tabulky s horizontálním sloučením buněk
Dále vytvoříme tabulku a použijeme horizontální slučování buněk pomocí vlastností poskytovaných Aspose.Words for .NET. Použijte následující kód:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Tato buňka je sloučena s předchozí a měla by být prázdná.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Zde použijeme tvůrce dokumentů k vytvoření tabulky a nastavení vlastností horizontálního sloučení buněk. Používáme`HorizontalMerge` majetek z`CellFormat` objekt k určení typu horizontálního sloučení, které se má použít pro každou buňku. Použitím`CellMerge.First` při používání sloučíme první buňku s další`CellMerge.Previous` sloučíme aktuální buňku s předchozí buňkou.`CellMerge.None` označuje, že buňka by neměla být sloučena.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s buňkami sloučenými vodorovně. Použijte následující kód:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázka zdrojového kódu pro horizontální sloučení pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Tato buňka je sloučena s předchozí a měla by být prázdná.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak horizontálně sloučit buňky v tabulce v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově použít horizontální slučování buněk v tabulkách aplikace Word. Tato funkce umožňuje vytvářet složitější rozvržení tabulek a lépe organizovat data.