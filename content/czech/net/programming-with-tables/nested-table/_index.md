---
title: Vnořená tabulka
linktitle: Vnořená tabulka
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit vnořenou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/nested-table/
---

V tomto tutoriálu se naučíme, jak vytvořit vnořenou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete schopni vytvářet vnořené tabulky v dokumentech aplikace Word programově.

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

## Krok 3: Vytvoření vnořené tabulky
Dále vytvoříme vnořenou tabulku vložením buněk do vnější tabulky a vytvořením nové tabulky uvnitř první buňky. Použijte následující kód:

```csharp
// Vložte první buňku vnější tabulky
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Vložte druhou buňku vnější tabulky
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Ukončení vnějšího stolu
builder. EndTable();

// Přesuňte se do první buňky vnější tabulky
builder.MoveTo(cell.FirstParagraph);

// Sestavte vnitřní stůl
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Konec vnitřního stolu
builder. EndTable();
```

Zde používáme tvůrce dokumentů k vložení buněk a obsahu do vnější tabulky. Poté přesuneme kurzor tvůrce dokumentů do první buňky vnější tabulky a uvnitř vytvoříme novou tabulku vložením buněk a obsahu.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s vnořenou tabulkou. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro vnořenou tabulku pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Toto volání je důležité pro vytvoření vnořené tabulky v první tabulce.
	//Bez tohoto volání budou buňky vložené níže připojeny k vnější tabulce.
	builder.EndTable();
	// Přesuňte se do první buňky vnější tabulky.
	builder.MoveTo(cell.FirstParagraph);
	// Sestavte vnitřní stůl.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vytvořit vnořenou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově vytvářet vnořené tabulky podle vašich konkrétních potřeb v dokumentech aplikace Word.
