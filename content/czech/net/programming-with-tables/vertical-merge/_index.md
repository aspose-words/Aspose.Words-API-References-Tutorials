---
title: Vertikální sloučení
linktitle: Vertikální sloučení
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se svisle sloučit buňky v tabulce v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/vertical-merge/
---

V tomto tutoriálu se naučíme vertikální sloučení buněk v tabulce v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci svisle sloučit buňky v tabulkách v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu
Chcete-li spustit textový editor s dokumentem, postupujte takto:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte nový dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Vertikální sloučení buněk
Dále sloučíme buňky svisle v tabulce. Použijte následující kód:

```csharp
// Vložte buňku
builder. InsertCell();

// Aplikujte svislé sloučení na první buňku
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Vložte další buňku
builder. InsertCell();

// Na buňku nepoužít žádné svislé sloučení
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Vložte buňku
builder. InsertCell();

// Aplikujte vertikální sloučení s předchozí buňkou
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Vložte další buňku
builder. InsertCell();

// Na buňku nepoužít žádné svislé sloučení
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Ukončete vytváření tabulky
builder. EndTable();
```

V tomto kódu používáme konstruktor DocumentBuilder k vkládání buněk do tabulky. Vertikální sloučení aplikujeme na buňky pomocí vlastnosti CellFormat.VerticalMerge. CellMerge.First používáme pro první sloučení buněk, CellMerge.Previous pro sloučení s předchozí buňkou a CellMerge.None pro žádné vertikální sloučení.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme uložit upravený dokument se sloučenými buňkami. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázka zdrojového kódu pro vertikální sloučení pomocí Aspose.Words pro .NET 
```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Tato buňka je svisle sloučena s buňkou výše a měla by být prázdná.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili svisle sloučit buňky v tabulce v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete snadno sloučit buňky Vertikálně v tabulkách.