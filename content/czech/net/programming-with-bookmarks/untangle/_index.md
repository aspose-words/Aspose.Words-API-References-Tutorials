---
title: Rozmotat v dokumentu Word
linktitle: Rozmotat v dokumentu Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak rozmotat vnořené záložky ve wordovém dokumentu v sousedních řádcích tabulky pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/untangle/
---

V tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci Untangle v knihovně Aspose.Words for .NET. Tato funkce rozloží vnořené záložky, které jsou v sousedních řádcích tabulky.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Procházení záložek dokumentu

Smyčku foreach používáme k procházení všech záložek přítomných v dokumentu:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Kód pro manipulaci se záložkami zde
}
```

## Krok 2: Získejte nadřazené řádky ze záložek

 Používáme`GetAncestor` metody pro načtení nadřazených řádků počátečních a koncových uzlů záložky:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Krok 3: Rozbalte vnořené záložky

Pokud jsou nalezeny oba nadřazené řádky a záložka začíná a končí v sousedních řádcích, přesuneme koncový uzel záložky na konec posledního odstavce poslední buňky v horním řádku:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Příklad zdrojového kódu pro Untangle pomocí Aspose.Words pro .NET

Zde je úplný příklad zdrojového kódu pro rozpletení vnořených záložek pomocí Aspose.Words pro .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Získejte nadřazený řádek koncového uzlu záložky i záložky.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Pokud jsou oba řádky nalezeny v pořádku a začátek a konec záložky jsou obsaženy v sousedních řádcích,
		// přesunout koncový uzel záložky na konec posledního odstavce v poslední buňce horního řádku.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Untangle v Aspose.Words pro .NET. Postupovali jsme podle podrobného průvodce, jak rozmotat vnořené záložky v sousedních řádcích tabulky.

### FAQ

#### Otázka: Funguje funkce Untangle pouze s vnořenými záložkami v sousedních řádcích tabulky?

Odpověď: Ano, funkce Untangle je navržena speciálně pro rozmotání vnořených záložek, které jsou v sousedních řádcích tabulky. Pokud se záložky nenacházejí v sousedních řádcích, tato funkce nebude použitelná.

#### Otázka: Jak mohu identifikovat vnořené záložky v dokumentu aplikace Word?

Odpověď: Vnořené záložky můžete identifikovat procházením záložek v dokumentu a kontrolou, zda jsou počáteční a koncová záložka v sousedních řádcích tabulky. Zdrojový kód uvedený v tomto článku můžete použít jako výchozí bod k implementaci této funkce.

#### Otázka: Mění funkce Unscramble obsah původního dokumentu?

Odpověď: Ano, funkce Untangle upravuje původní dokument přesunutím koncového uzlu záložky na konec posledního odstavce poslední buňky v horním řádku. Před použitím této funkce nezapomeňte uložit záložní kopii dokumentu.

#### Otázka: Jak mohu rozložit vnořené záložky v jiných typech prvků dokumentu, jako jsou oddíly nebo odstavce?

Odpověď: Funkce Untangle uvedená v tomto článku je speciálně navržena k rozmotání vnořených záložek v sousedních řádcích tabulky. Pokud chcete rozmotat vnořené záložky v jiných prvcích dokumentu, budete muset odpovídajícím způsobem upravit kód a použít vhodné metody pro přístup k požadovaným prvkům.

#### Otázka: Existují nějaké jiné metody pro rozmotání vnořených záložek v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Metoda uvedená v tomto článku je běžnou metodou pro rozpletení vnořených záložek v sousedních řádcích tabulky. Mohou však existovat i jiné přístupy nebo techniky v závislosti na konkrétních potřebách vašeho projektu. Můžete se podívat na[Aspose.Words for .NET API odkazy](https://reference.aspose.com/words/net/) k dalšímu prozkoumání dostupných funkcí.