---
title: Nastavte formátování řádku tabulky
linktitle: Nastavte formátování řádku tabulky
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením formátování řádků tabulky pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

V tomto tutoriálu vás provedeme krok za krokem procesem nastavení formátování řádků tabulky pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak upravit výšku a odsazení řádku tabulky v dokumentech aplikace Word pomocí Aspose.Words for .NET.

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

## Krok 3: Vytvořte novou tabulku a přidejte buňku
Chcete-li začít vytvářet tabulku, použijeme`StartTable()` metoda konstruktoru dokumentu, pak přidáme buňku do tabulky pomocí`InsertCell()` metoda.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Krok 4: Definujte formátování řádku
 Nyní můžeme nastavit formátování řádků přístupem k`RowFormat` objekt`DocumentBuilder` objekt. Pomocí odpovídajících vlastností můžeme nastavit výšku řádku a okraje (odsazení).

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Krok 5: Nastavte okraje tabulky
 Dále můžeme nastavit odsazení tabulky přístupem k odpovídajícím vlastnostem`Table` objekt. Tyto okraje se použijí na všechny řádky tabulky.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Krok 6: Přidejte obsah do řádku
 Nakonec můžeme přidat obsah do řádku pomocí nástroje pro tvorbu dokumentů`Writeln()` metoda.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Krok 7: Dokončete tabulku a uložte dokument
v

 konec, dokončíme vytváření tabulky pomocí`EndRow()` a`EndTable()` metodou, pak upravený dokument uložíme do souboru.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Ukázkový zdrojový kód pro nastavení formátování řádků tabulky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Tyto vlastnosti formátování jsou nastaveny v tabulce a jsou aplikovány na všechny řádky v tabulce.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak nastavit formátování řádků tabulky pomocí Aspose.Words pro .NET. Podle tohoto podrobného průvodce můžete snadno upravit výšku řádku tabulky a okraje v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete přizpůsobit vizuální rozvržení vašich stolů svým konkrétním potřebám.