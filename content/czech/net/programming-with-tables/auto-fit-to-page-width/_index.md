---
title: Automaticky přizpůsobit šířce stránky
linktitle: Automaticky přizpůsobit šířce stránky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak automaticky přizpůsobit tabulku šířce stránky v dokumentu Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/auto-fit-to-page-width/
---

V tomto tutoriálu se naučíme, jak používat Aspose.Words pro .NET k automatickému přizpůsobení tabulky šířce stránky v dokumentu aplikace Word. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete schopni programově manipulovat s tabulkami v dokumentech Wordu.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření a konfigurace dokumentu
Chcete-li spustit textový procesor s tabulkou, musíme vytvořit dokument a nakonfigurovat generátor dokumentů. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a generátor dokumentů
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 3: Vložení a konfigurace tabulky
Dále do dokumentu vložíme tabulku o šířce, která zabírá polovinu šířky stránky. Použijte následující kód:

```csharp
// Vložte tabulku a nakonfigurujte její šířku
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Zde pomocí nástroje pro tvorbu dokumentů začneme vytvářet tabulku, vložíme buňky a nastavíme preferovanou šířku tabulky na 50 % šířky stránky. Poté do každé buňky přidáme text.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s tabulkou upravenou na šířku stránky. Použijte následující kód:

```csharp
// Uložte upravený dokument
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.
  
### Ukázkový zdrojový kód pro Auto Fit To Page Width pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Vložte tabulku o šířce, která zabírá polovinu šířky stránky.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak automaticky přizpůsobit tabulku šířce stránky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově manipulovat s tabulkami v dokumentech aplikace Word. Tato funkce umožňuje dynamicky přizpůsobovat šířku tabulky podle stránky a nabízí tak profesionální a vizuálně přitažlivý dokument.