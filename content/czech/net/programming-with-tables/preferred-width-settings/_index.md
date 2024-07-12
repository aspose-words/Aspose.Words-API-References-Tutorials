---
title: Nastavení preferované šířky
linktitle: Nastavení preferované šířky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit preferované šířky buněk tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/preferred-width-settings/
---

V tomto tutoriálu se naučíme, jak nastavit preferované nastavení šířky pro buňky tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci určit různé preferované šířky pro buňky tabulky v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu a inicializace generátoru dokumentů
Chcete-li spustit textový editor s dokumentem a generátorem dokumentů, postupujte takto:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvoření dokumentu
Document doc = new Document();

// Inicializujte generátor dokumentů
DocumentBuilder builder = new DocumentBuilder(doc);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Sestavení stolu s preferovanou šířkou
Dále vytvoříme tabulku se třemi buňkami, které mají různé preferované šířky. Použijte následující kód:

```csharp
// Začátek tabulky
builder. StartTable();

// Vložte buňku absolutní velikosti
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Vložit buňku relativní velikosti (v procentech)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Vložte buňku s automatickou velikostí
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Konec stolu
builder. EndTable();
```

Zde použijeme tvůrce dokumentů k vytvoření tabulky se třemi buňkami. První buňka má preferovanou šířku 40 bodů, druhá buňka má preferovanou šířku 20 % šířky tabulky a třetí buňka má automatickou preferovanou šířku, která upravuje

  v závislosti na dostupném prostoru.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s preferovaným nastavením šířky definovaným pro buňky tabulky. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro nastavení preferované šířky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Vložte řádek tabulky složený ze tří buněk, které mají různé preferované šířky.
	builder.StartTable();
	// Vložte buňku absolutní velikosti.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Vložte buňku relativní (procentuální) velikosti.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Vložte buňku s automatickou velikostí.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak nastavit preferovaná nastavení šířky pro buňky tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete přizpůsobit šířky buněk tabulky svým konkrétním potřebám v dokumentech aplikace Word.