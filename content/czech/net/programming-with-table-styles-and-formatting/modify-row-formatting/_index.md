---
title: Upravit formátování řádků
linktitle: Upravit formátování řádků
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce změnou formátování řádku tabulky pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

V tomto tutoriálu vás provedeme krok za krokem procesem změny formátování řádku tabulky pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak změnit okraje, výšku a zalomení řádku řádku tabulky v dokumentech aplikace Word pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Zde se nachází váš dokument aplikace Word. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte existující dokument
 Dále musíte načíst existující dokument aplikace Word do instance souboru`Document` třída.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Krok 3: Otevřete řádek, který chcete upravit
 Chcete-li změnit formátování řádku tabulky, musíme přejít na konkrétní řádek v tabulce. Používáme`GetChild()`a`FirstRow` metody pro získání odkazu na první řádek tabulky.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Krok 4: Změňte formátování řádku
 Nyní můžeme změnit formátování řádku pomocí vlastností the`RowFormat` třída. Můžeme například odstranit okraje řádku, nastavit automatickou výšku a povolit zalomení řádku.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Ukázka zdrojového kódu pro úpravu formátování řádků pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Načtěte první řádek v tabulce.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Závěr
V tomto tutoriálu jsme se naučili, jak změnit formátování řádku tabulky pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno upravit ohraničení, výšku a zalomení řádků v tabulkách v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete přizpůsobit vizuální rozvržení vašich stolů svým konkrétním potřebám.