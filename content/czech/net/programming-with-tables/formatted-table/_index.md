---
title: Formátovaná tabulka
linktitle: Formátovaná tabulka
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit formátovanou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/formatted-table/
---

V tomto tutoriálu se naučíme, jak vytvořit formátovanou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově vytvářet tabulky s vlastním formátováním v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu a inicializace generátoru dokumentů
Abychom mohli začít vytvářet formátovanou tabulku, musíme vytvořit nový dokument a inicializovat generátor dokumentů. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a inicializujte generátor dokumentů
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Vytvoření formátované tabulky
Dále vytvoříme formátovanou tabulku pomocí metod poskytnutých tvůrcem dokumentů. Použijte následující kód:

```csharp
// Začněte se stavbou pole
Table table = builder. StartTable();

// Konstrukce řádku záhlaví tabulky
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Konstrukce těla pole
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Konec konstrukce pole
builder. EndTable();
```

 Zde používáme tvůrce dokumentů k sestavení tabulky krok za krokem. Začínáme telefonátem`StartTable()` k inicializaci tabulky. Pak použijeme`InsertCell()` vkládat buňky a`Write()` přidat obsah do každé buňky. K definování formátování řádků, buněk a textu tabulky používáme také různé vlastnosti formátování.

## Krok 4: Uložte dokument
Nakonec musíme uložit dokument obsahující formátovanou tabulku. Použijte následující kód:

```csharp
// Uložte dokument
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázka zdrojového kódu pro formátovanou tabulku pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Formátování na šířku tabulky musí být použito poté, co je v tabulce přítomen alespoň jeden řádek.
	table.LeftIndent = 20.0;
	// Nastavte výšku a definujte pravidlo výšky pro řádek záhlaví.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Šířku této buňky nemusíme zadávat, protože je zděděna z předchozí buňky.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Resetovat výšku a definovat jiné pravidlo výšky pro tělo stolu.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Obnovit formátování písma.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak vytvořit formátovanou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově vytvářet vlastní tabulky se specifickým formátováním v dokumentech aplikace Word. Tato funkce vám umožňuje prezentovat a strukturovat data vizuálně přitažlivým a organizovaným způsobem.