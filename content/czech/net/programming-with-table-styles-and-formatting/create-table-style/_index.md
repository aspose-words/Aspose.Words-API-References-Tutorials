---
title: Vytvořit styl tabulky
linktitle: Vytvořit styl tabulky
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce vytvořením vlastního stylu tabulky pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/create-table-style/
---

V tomto tutoriálu vás provedeme krok za krokem procesem vytvoření stylu tabulky pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak vytvořit vlastní styl pro vaše tabulky v dokumentech aplikace Word pomocí Aspose.Words for .NET.

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
Chcete-li začít vytvářet tabulku, použijeme`StartTable()` metodou tvůrce dokumentů, pak přidáme buňky do tabulky pomocí`InsertCell()` a obsah buněk zapíšeme do pomocí the`Write()` metoda.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Krok 4: Vytvořte styl tabulky
 Nyní můžeme vytvořit styl tabulky pomocí`TableStyle` třída a`Add()` metoda z dokumentu`s `Kolekce stylů. Definujeme vlastnosti stylu, jako jsou okraje, okraje a odsazení.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Krok 5: Použijte styl tabulky na tabulku
 Nakonec použijeme styl tabulky, který jsme vytvořili, na tabulku pomocí`Style` vlastnost stolu.

```csharp
table.Style = tableStyle;
```

## Krok 6: Uložte upravený dokument
Nakonec upravený dokument uložte do souboru. Můžete zvolit vhodný název a umístění výstupního dokumentu.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

gratuluji! Nyní jste vytvořili vlastní styl pro vaši tabulku pomocí Aspose.Words for .NET.

### Ukázka zdrojového kódu pro vytvoření stylu tabulky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak vytvořit styl tabulky pomocí Aspose.Words pro .NET. Podle tohoto podrobného průvodce můžete snadno přizpůsobit styl tabulek v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete zlepšit vizuální prezentaci vašich dokumentů Word a splnit specifické potřeby.