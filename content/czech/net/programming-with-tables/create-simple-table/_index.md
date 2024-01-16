---
title: Vytvořte jednoduchou tabulku
linktitle: Vytvořte jednoduchou tabulku
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit jednoduchou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/create-simple-table/
---

V tomto tutoriálu se naučíme, jak vytvořit jednoduchou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově vytvářet vlastní tabulky v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu a inicializace generátoru dokumentů
Abychom mohli začít sestavovat tabulku, musíme vytvořit nový dokument a inicializovat tvůrce dokumentů. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a inicializujte generátor dokumentů
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Sestavení pole
Dále vytvoříme tabulku pomocí metod poskytnutých tvůrcem dokumentů. Použijte následující kód:

```csharp
// Začněte se stavbou pole
builder. StartTable();

// Konstrukce první buňky první řady
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Konstrukce druhé buňky první řady
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Chcete-li ukončit první řádek a začít nový řádek, zavolejte následující metodu
builder. EndRow();

// Konstrukce první buňky druhé řady
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Konstrukce druhé buňky druhé řady
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Zavoláním další metody ukončíte druhý řádek
builder. EndRow();

// Indikace, že konstrukce stolu je dokončena
builder. EndTable();
```

 Zde používáme tvůrce dokumentů k sestavení tabulky krok za krokem. Začínáme telefonátem`StartTable()` pro inicializaci tabulky a poté použijte`InsertCell()` vkládat buňky a`Write()` přidat obsah do každé buňky. Také používáme`EndRow()` ukončit řádek a začít nový řádek. Nakonec si zavoláme`EndTable()` pro označení, že konstrukce stolu je dokončena.

## Krok 4: Uložte dokument
Nakonec musíme ušetřit

  dokument s vytvořenou tabulkou. Použijte následující kód:

```csharp
// Uložte dokument
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázka zdrojového kódu pro vytvoření jednoduché tabulky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Začněte stavět stůl.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Sestavte druhou buňku.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Zavolejte následující metodu pro ukončení řádku a zahájení nového řádku.
	builder.EndRow();
	// Vytvořte první buňku druhého řádku.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Sestavte druhou buňku.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Signál, že jsme dokončili stavbu stolu.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vytvořit jednoduchou tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově vytvářet vlastní tabulky v dokumentech aplikace Word. Tato funkce umožňuje formátovat a organizovat data strukturovaným a jasným způsobem.