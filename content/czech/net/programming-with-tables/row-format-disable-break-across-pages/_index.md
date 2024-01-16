---
title: Formát řádku Zakázat zalomení mezi stránkami
linktitle: Formát řádku Zakázat zalomení mezi stránkami
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zakázat zalomení řádku pro tabulku na více stránkách v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/row-format-disable-break-across-pages/
---

tomto tutoriálu se naučíme, jak zakázat zalomení řádku u vícestránkové tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci zakázat zalamování řádků pro všechny řádky v tabulce v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu
Chcete-li spustit textový editor s dokumentem, postupujte takto:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů a uveďte správný název souboru.

## Krok 3: Zakažte konec řádku tabulky
Dále zakážeme zalamování řádků pro všechny řádky v tabulce. Použijte následující kód:

```csharp
// Získejte tabulku
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Zakázat konec řádku pro všechny řádky v tabulce
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Zde používáme dokument k načtení první tabulky a poté iterujeme všechny řádky v tabulce pomocí smyčky foreach. Uvnitř smyčky zakážeme zalamování řádků pro každý řádek nastavením`RowFormat.AllowBreakAcrossPages`majetek do`false`.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s vypnutým zalomením řádku tabulky. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro formát řádků Zakázat přerušení mezi stránkami pomocí Aspose.Words for .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Zakázat rozdělení na stránky pro všechny řádky v tabulce.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak zakázat zalomení řádku u vícestránkové tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete toto zakázání použít na tabulky v dokumentech aplikace Word.