---
title: Vložit tabulku z HTML
linktitle: Vložit tabulku z HTML
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit tabulku z HTML do dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/insert-table-from-html/
---

tomto tutoriálu se naučíme, jak vložit tabulku do dokumentu Word z HTML pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete schopni vkládat tabulky z HTML do dokumentů Wordu programově.

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

## Krok 3: Vložení tabulky z HTML
Dále tabulku vložíme do dokumentu pomocí HTML kódu. Použijte následující kód:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Zde používáme`InsertHtml` metoda tvůrce dokumentů pro vložení HTML obsahujícího tabulku. Zadaný kód HTML vytvoří tabulku se dvěma řádky a dvěma buňkami v každém řádku. Obsah tabulky si můžete upravit úpravou HTML kódu podle svých potřeb.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s tabulkou vloženou z HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro Insert Table From Html pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Všimněte si, že AutoFitSettings se nevztahuje na tabulky vložené z HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vložit tabulku do dokumentu aplikace Word z HTML pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete vkládat tabulky z HTML do dokumentů aplikace Word programově. Tato funkce umožňuje převádět a importovat tabulková data ze zdrojů HTML do dokumentů aplikace Word.
