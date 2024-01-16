---
title: Formát Tabulky A Buňky S Různými Hranicemi
linktitle: Formát Tabulky A Buňky S Různými Hranicemi
second_title: Aspose.Words API pro zpracování dokumentů
description: Krok za krokem průvodce formátováním tabulky a buňky s různými okraji pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

tomto tutoriálu vás provedeme krok za krokem procesem formátování tabulky a buňky s různými okraji pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak použít vlastní ohraničení na konkrétní tabulku a buňky v dokumentech aplikace Word pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený dokument aplikace Word. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvořte nový dokument a tvůrce dokumentů
 Dále musíte vytvořit novou instanci souboru`Document` třída a konstruktor dokumentu pro tento dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vytvořte novou tabulku a přidejte buňky
Chcete-li začít vytvářet tabulku, použijeme`StartTable()` metodou tvůrce dokumentů, pak přidáme buňky do tabulky pomocí`InsertCell()` a obsah buněk zapíšeme do pomocí the`Writeln()` metoda.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Nastavte okraje pro celou tabulku.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Nastavit odsazení pro tuto buňku.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Zadejte pro druhou buňku jiné odsazení buňky.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Vymazat formátování buněk z předchozích operací.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Vytvořte silnější ohraničení pro první buňku v tomto řádku. Bude to jiné
// vzhledem k hranicím definovaným pro tabulku.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Krok 4: Uložte dokument

  pozměněno
Nakonec upravený dokument uložte do souboru. Můžete zvolit vhodný název a umístění výstupního dokumentu.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

gratuluji! Nyní jste pomocí Aspose.Words for .NET naformátovali tabulku a buňku s různými okraji.

### Ukázka zdrojového kódu pro formátování tabulky a buňky s různými okraji pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Nastavte okraje pro celou tabulku.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Nastavte stínování buňky pro tuto buňku.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Zadejte jiné stínování buňky pro druhou buňku.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Vymažte formátování buňky z předchozích operací.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Vytvořte větší ohraničení pro první buňku tohoto řádku. Tohle bude jiné
	// ve srovnání s hranicemi stanovenými pro tabulku.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili formátovat tabulku a buňku s různými okraji pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno přizpůsobit ohraničení tabulek a buněk v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete zlepšit vizuální prezentaci vašich dokumentů Word a splnit specifické potřeby.