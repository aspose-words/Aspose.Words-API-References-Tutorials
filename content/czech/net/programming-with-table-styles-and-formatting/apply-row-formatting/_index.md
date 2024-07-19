---
title: Použít formátování řádků
linktitle: Použít formátování řádků
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem k použití formátování řádků na tabulku pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

tomto tutoriálu vás provedeme krok za krokem procesem použití formátování řádků na tabulku pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto kurzu budete mít jasnou představu o tom, jak formátovat řádky tabulky v dokumentech aplikace Word pomocí Aspose.Words for .NET.

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

## Krok 3: Založte novou desku
 Chcete-li použít formátování řádků, musíme nejprve spustit novou tabulku pomocí`StartTable()` metoda konstruktoru dokumentu.

```csharp
Table table = builder. StartTable();
```

## Krok 4: Vložte buňku a přejděte na formát řádku
Nyní můžeme vložit buňku do tabulky a získat přístup k formátu řádku pro tuto buňku pomocí nástroje pro tvorbu dokumentů`InsertCell()`a`RowFormat` metody.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Krok 5: Nastavte výšku řádku
 Pro nastavení výšky řádku použijeme`Height`a`HeightRule` vlastnosti formátu řádků. V tomto příkladu nastavíme výšku řádku 100 bodů a použijeme`Exactly` pravidlo.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Krok 6: Definujte formátování tabulky
 Některé vlastnosti formátování lze nastavit na samotné tabulce a použijí se na všechny řádky tabulky. V tomto příkladu nastavíme vlastnosti okraje tabulky pomocí`LeftPadding`, `RightPadding`, `TopPadding`a`BottomPadding` vlastnosti.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Krok 7: Přidejte obsah do řádku
Teď můžeme

 Do řádku přidáme obsah pomocí metod konstruktoru dokumentu. V tomto příkladu používáme`Writeln()` metoda pro přidání textu na řádek.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Krok 8: Dokončete čáru a stůl
 Jakmile přidáme obsah do řádku, můžeme řádek ukončit pomocí`EndRow()` a poté tabulku ukončete pomocí`EndTable()` metoda.

```csharp
builder. EndRow();
builder. EndTable();
```

## Krok 9: Uložte upravený dokument
Nakonec upravený dokument uložíme do souboru. Můžete zvolit vhodný název a umístění výstupního dokumentu.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

gratuluji! Nyní jste použili formátování řádků na tabulku pomocí Aspose.Words for .NET.

### Ukázkový zdrojový kód pro použití formátování řádků pomocí Aspose.Words pro .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak aplikovat formátování řádků na tabulku pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno integrovat tuto funkci do svých projektů C#. Manipulace s formátováním řádků tabulky je základním aspektem zpracování dokumentů a Aspose.Words nabízí výkonné a flexibilní API, jak toho dosáhnout. S těmito znalostmi můžete zlepšit vizuální prezentaci vašich dokumentů Word a splnit specifické požadavky.