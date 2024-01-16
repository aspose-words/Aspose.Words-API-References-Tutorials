---
title: Záložka sloupce tabulky v dokumentu aplikace Word
linktitle: Záložka sloupce tabulky v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit záložku sloupce tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/bookmark-table-columns/
---

V tomto článku prozkoumáme zdrojový kód C# výše, abychom porozuměli tomu, jak používat funkci Bookmark Table Columns v knihovně Aspose.Words for .NET. Tato funkce vám umožňuje označit konkrétní sloupec tabulky v dokumentu aplikace Word a získat přístup k obsahu tohoto sloupce.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Vytvoření tabulky

 Před vytvořením záložky na sloupci tabulky musíme nejprve vytvořit tabulku pomocí a`DocumentBuilder`objekt. V našem příkladu vytvoříme tabulku se dvěma řádky a dvěma sloupci:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Krok 2: Vytvoření záložky sloupce

 Používáme`StartBookmark` způsob vytvoření záložky na konkrétním sloupci tabulky. V našem příkladu používáme pro záložku název „MyBookmark“:

```csharp
builder. StartBookmark("MyBookmark");
```

## Krok 3: Přístup k obsahu sloupce

 Procházíme všechny záložky v dokumentu a zobrazujeme jejich názvy. Pokud je záložkou sloupec, přistupujeme k obsahu tohoto sloupce pomocí indexu sloupce a`GetText` metoda:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Příklad zdrojového kódu pro sloupce tabulky záložek pomocí Aspose.Words pro .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje vytvoření záložky ve sloupci tabulky pomocí Aspose.Words for .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom porozuměli tomu, jak používat funkci Bookmark Table Columns Aspose.Words for .NET. Postupovali jsme podle podrobného průvodce, jak označit konkrétní sloupec tabulky v dokumentu aplikace Word a přejít na obsah tohoto sloupce.

### Časté dotazy pro sloupce tabulky záložek v dokumentu aplikace Word

#### Otázka: Jaké jsou předpoklady pro použití funkce "Záložky pro sloupce tabulky" v Aspose.Words for .NET?

A: Chcete-li použít funkci "Záložky pro sloupce tabulky" v Aspose.Words pro .NET, musíte mít základní znalosti jazyka C#. Potřebujete také vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

#### Otázka: Jak vytvořit tabulku se sloupci v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 A: Chcete-li vytvořit tabulku se sloupci v dokumentu aplikace Word pomocí Aspose.Words pro .NET, můžete použít`DocumentBuilder` objekt pro vložení buněk a obsahu do tabulky. Zde je ukázkový kód:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Otázka: Jak vytvořit záložku sloupce tabulky pomocí Aspose.Words pro .NET?

 A: Chcete-li vytvořit záložku ve sloupci tabulky pomocí Aspose.Words pro .NET, můžete použít`StartBookmark` metoda`DocumentBuilder` objekt pro spuštění záložky na konkrétním sloupci tabulky. Zde je ukázkový kód:

```csharp
builder.StartBookmark("MyBookmark");
```

#### Otázka: Jak přistupovat k obsahu sloupců tabulky ze záložky pomocí Aspose.Words for .NET?

Odpověď: Chcete-li přistupovat k obsahu sloupce tabulky ze záložky pomocí Aspose.Words for .NET, můžete procházet všechny záložky v dokumentu, zkontrolovat, zda je záložka sloupec, a použít index sloupce pro přístup k obsahu ten sloupec. Zde je ukázkový kód:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Udělejte něco s obsahem sloupce...
         }
     }
}
```

#### Otázka: Existuje omezení počtu sloupců, které mohu vytvořit v tabulce se záložkami sloupců?

Odpověď: Neexistuje žádný konkrétní limit na počet sloupců, které můžete vytvořit v tabulce se záložkami sloupců pomocí Aspose.Words for .NET. Limit závisí hlavně na zdrojích dostupných ve vašem systému a specifikacích formátu souboru Word, který používáte. Doporučuje se však nevytvářet příliš velké množství sloupců, protože to může ovlivnit výkon a čitelnost výsledného dokumentu.