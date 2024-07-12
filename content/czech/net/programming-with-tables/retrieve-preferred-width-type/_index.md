---
title: Načíst preferovaný typ šířky
linktitle: Načíst preferovaný typ šířky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak načíst typ a preferovanou hodnotu šířky buňky v tabulce aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/retrieve-preferred-width-type/
---

V tomto tutoriálu se naučíme, jak získat preferovaný typ šířky a jeho hodnotu z buňky tabulky v dokumentu Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci získat preferovaný typ šířky (absolutní, relativní nebo automatický) a jeho hodnotu pro konkrétní buňku v tabulkách dokumentů aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu
Chcete-li spustit textový editor s dokumentem, postupujte takto:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů a uveďte správný název souboru.

## Krok 3: Načtení preferovaného typu šířky a hodnoty
Dále načteme preferovaný typ šířky a jeho hodnotu pro konkrétní buňku tabulky. Použijte následující kód:

```csharp
// Získejte tabulku
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Aktivujte automatické nastavení stolu
table. AllowAutoFit = true;

//Načtěte první buňku prvního řádku
Cell firstCell = table.FirstRow.FirstCell;

// Načtěte preferovaný typ šířky a jeho hodnotu
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Zde použijeme dokument k načtení první tabulky, poté povolíme automatické přizpůsobení tabulky`AllowAutoFit` vlastnictví. Poté načteme první buňku prvního řádku tabulky. Z této buňky můžeme získat preferovaný typ šířky pomocí`PreferredWidth.Type` majetku a jeho hodnoty s`PreferredWidth.Value` vlastnictví.

### Ukázka zdrojového kódu pro Retrieve Preferred Width Type pomocí Aspose.Words for .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Závěr
V tomto tutoriálu jsme se naučili, jak získat preferovaný typ šířky a jeho hodnotu z buňky tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete získat tyto informace pro konkrétní buňky v tabulkách dokumentů aplikace Word.