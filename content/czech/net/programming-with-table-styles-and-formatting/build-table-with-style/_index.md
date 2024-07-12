---
title: Sestavit Stůl Se Stylem
linktitle: Sestavit Stůl Se Stylem
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce vytvořením tabulky s vlastním stylem pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

tomto tutoriálu vás provedeme krok za krokem procesem vytvoření stylizované tabulky pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak vytvořit tabulku s vlastním stylem v dokumentech aplikace Word pomocí Aspose.Words for .NET.

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

## Krok 3: Vytvořte novou tabulku a vložte buňku
 Chcete-li začít sestavovat tabulku, použijeme`StartTable()` metodu tvůrce dokumentů, pak vložíme buňku do tabulky pomocí`InsertCell()` metoda.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Krok 4: Definujte styl tabulky
 Nyní můžeme nastavit styl tabulky pomocí`StyleIdentifier` vlastnictví. V tomto příkladu používáme styl "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Krok 5: Použijte možnosti stylu na tabulku
 Můžeme určit, které charakteristiky by měly být formátovány stylem pomocí`StyleOptions`vlastnost pole. V tomto příkladu použijeme následující možnosti: "FirstColumn", "RowBands" a "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Krok 6: Automaticky upravte velikost tabulky
 Chcete-li automaticky upravit velikost pole na základě jeho obsahu, použijeme`AutoFit()` metoda s`AutoFitBehavior.AutoFitToContents` chování.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Krok 7: Přidejte obsah do buněk
 Nyní můžeme přidat obsah do buněk pomocí`Writeln()`a`InsertCell()` metody tvůrce dokumentů. V tomto příkladu přidáme záhlaví pro položky „Položka“ a „Množství (

kg)“ a odpovídající údaje.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Krok 8: Uložte upravený dokument
Nakonec upravený dokument uložíme do souboru. Můžete zvolit vhodný název a umístění výstupního dokumentu.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

gratuluji! Nyní jste vytvořili vlastní stylizovanou tabulku pomocí Aspose.Words pro .NET.

### Ukázka zdrojového kódu pro Build Table With Style pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Před nastavením jakéhokoli formátování tabulky musíme nejprve vložit alespoň jeden řádek.
	builder.InsertCell();
	// Nastavte použitý styl tabulky na základě jedinečného identifikátoru stylu.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Použijte, které prvky by měly být formátovány stylem.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak vytvořit stylizovanou tabulku pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno přizpůsobit styl tabulek v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete zlepšit vizuální prezentaci vašich dokumentů Word a splnit specifické potřeby.