---
title: Vložit tabulku přímo
linktitle: Vložit tabulku přímo
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit tabulku přímo do dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/insert-table-directly/
---

V tomto tutoriálu se naučíme, jak přímo vložit tabulku do dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci vkládat tabulky přímo do dokumentů aplikace Word programově.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu a tabulky
Chcete-li spustit textový procesor s polem, musíme vytvořit nový dokument a pole inicializovat. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvoření dokumentu
Document doc = new Document();

//Vytvořte pole
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Sestavení pole
Dále vytvoříme tabulku přidáním řádků a buněk. Jako příklad použijte následující kód:

```csharp
// Vytvořte první řadu
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Vytvořte první buňku
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplikujte buňku pro druhou buňku v řádku
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Zde vytvoříme řádek s`AllowBreakAcrossPages` vlastnost nastavena na`true` umožňující zalamování stránek mezi řádky. Poté vytvoříme buňku s barevným pozadím, pevnou šířkou a určeným textovým obsahem. Tuto buňku pak duplikujeme a vytvoříme druhou buňku v řadě.

## Krok 4: Auto Fit Table
Pro správné formátování tabulky můžeme použít automatické úpravy. Použijte následující kód:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Tento řádek kódu aplikuje automatické přizpůsobení na základě pevných šířek sloupců.

## Krok 5: Registrace

  upravený dokument
Nakonec musíme upravený dokument uložit přímo s vloženou tabulkou. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro Vložit tabulku přímo pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Začneme vytvořením objektu tabulky. Všimněte si, že musíme předat objekt dokumentu
	//ke konstruktoru každého uzlu. Je to proto, že každý uzel, který vytvoříme, musí patřit
	// na nějaký dokument.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Zde bychom mohli zavolat SecureMinimum, aby za nás vytvořili řádky a buňky. Tato metoda se používá
	// abyste se ujistili, že zadaný uzel je platný. V tomto případě by platná tabulka měla mít alespoň jeden řádek a jednu buňku.
	// Místo toho si vytvoříme řádek a tabulku sami.
	// To by byl nejlepší způsob, jak toho dosáhnout, pokud bychom vytvářeli tabulku uvnitř algoritmu.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Nyní můžeme použít libovolné nastavení automatického přizpůsobení.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Poté bychom postup opakovali pro další buňky a řádky v tabulce.
	// Věci můžeme urychlit také klonováním existujících buněk a řádků.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak přímo vložit tabulku do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete vkládat tabulky přímo do dokumentů aplikace Word programově. Tato funkce vám umožňuje vytvářet a upravovat tabulky podle vašich konkrétních potřeb.