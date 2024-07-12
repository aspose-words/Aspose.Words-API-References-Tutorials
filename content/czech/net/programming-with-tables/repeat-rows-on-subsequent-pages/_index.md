---
title: Opakujte řádky na následujících stránkách
linktitle: Opakujte řádky na následujících stránkách
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se opakovat řádky tabulky na následujících stránkách v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

V tomto tutoriálu se naučíme, jak opakovat řádky tabulky na následujících stránkách dokumentu Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete schopni určit řádky, které se mají opakovat na následujících stránkách tabulky v dokumentech aplikace Word.

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

## Krok 3: Sestavení tabulky s opakovanými řádky
Dále vytvoříme tabulku s opakovanými řádky na následujících stránkách. Použijte následující kód:

```csharp
// Začátek tabulky
builder. StartTable();

// Konfigurace parametrů prvního řádku (řádky záhlaví)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//Vložte první buňku prvního řádku
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Vložte druhou buňku prvního řádku
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Nakonfigurujte parametry následujících řádků
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Smyčkou vložte buňky do následujících řádků
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Konec stolu
builder. EndTable();
```

 Zde používáme tvůrce dokumentů k vytvoření tabulky se dvěma řádky záhlaví a více řádky dat. The`RowFormat.HeadingFormat` parametry se používají k označení řádků záhlaví, které by se měly opakovat na následujících stránkách.

## Krok 4: Uložení upraveného dokumentu
Konečně USA

  potřeba uložit upravený dokument s řádky záhlaví opakujícími se na následujících stránkách tabulky. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro opakování řádků na následujících stránkách pomocí Aspose.Words pro .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak opakovat řádky tabulky na následujících stránkách dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete určit, které řádky se mají opakovat podle vašich konkrétních potřeb ve vašich dokumentech aplikace Word.