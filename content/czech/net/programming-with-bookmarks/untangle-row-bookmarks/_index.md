---
title: Rozmotat záložky řádků v dokumentu aplikace Word
linktitle: Rozmotat záložky řádků v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak rozmotat vnořené záložky řádků v dokumentu aplikace Word, abyste odstranili konkrétní řádky bez ovlivnění ostatních záložek.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/untangle-row-bookmarks/
---

tomto článku prozkoumáme zdrojový kód C# výše, abychom pochopili, jak používat funkci Untangle Row Bookmarks v knihovně Aspose.Words for .NET. Tato funkce umožňuje umístit konce záložek řádků na stejný řádek jako začátky záložek.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Načtení dokumentu

 Používáme`Document` třídy k načtení existujícího dokumentu ze souboru:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Krok 2: Rozbalte záložky řádku

 Používáme`Untangle` funkce pro rozpletení záložek z řádků. Tato funkce provádí vlastní úlohu umístění záložek konců řádků do stejného řádku, na kterém začíná záložka:

```csharp
Untangle(doc);
```

## Krok 3: Odstraňte řádek po záložce

 Používáme`DeleteRowByBookmark` funkce pro odstranění konkrétního řádku podle jeho záložky:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Krok 4: Zkontrolujte integritu ostatních záložek

Ověříme, že ostatní záložky nebyly poškozeny kontrolou, zda je stále přítomen konec záložky:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Příklad zdrojového kódu pro Untangle Row Bookmarks pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód pro rozpletení záložek z řádků pomocí Aspose.Words pro .NET:


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Tím se provede vlastní úkol umístit konce záložky řádku do stejného řádku se začátkem záložky.
	Untangle(doc);

	// Nyní můžeme snadno odstranit řádky záložkou, aniž bychom poškodili záložky jiných řádků.
	DeleteRowByBookmark(doc, "ROW2");

	// To je jen pro kontrolu, že druhá záložka nebyla poškozena.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Rozbalte zdrojový kód
```csharp

private void Untangle(Document doc)
        {
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
        }

```

#### Odstraňte zdrojový kód RowByBookmark
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Untangle Row Bookmarks v Aspose.Words for .NET. Postupovali jsme podle podrobného průvodce, jak rozmotat záložky řádků a odstranit konkrétní řádek bez poškození ostatních záložek.

### Časté dotazy pro rozpletení záložek řádků v dokumentu aplikace Word

#### Otázka: Funguje Unscramble Row Bookmarks pouze se záložkami řádků v tabulkách?

Odpověď: Ano, funkce Untangle Row Bookmarks je speciálně navržena k rozmotání záložek řádků, které jsou v tabulkách. Tuto funkci lze použít ke zpracování záložek řádků v polích a zajistit, aby konce záložek byly na stejném řádku jako začátek záložek.

#### Otázka: Mění funkce Unscramble Line Bookmarks obsah původního dokumentu?

Odpověď: Ano, funkce Dekódovat záložky řádků upravuje původní dokument přesunutím konců záložek řádků tak, aby byly umístěny na stejném řádku jako začátky záložek. Před použitím této funkce nezapomeňte uložit záložní kopii dokumentu.

#### Otázka: Jak mohu identifikovat záložky řádků v dokumentu aplikace Word?

Odpověď: Řádkové záložky se obvykle používají v tabulkách k označení konkrétních sekcí. Záložky řádků můžete identifikovat procházením záložek v dokumentu a kontrolou, zda jsou záložky v řádcích tabulky.

#### Otázka: Je možné rozmotat záložky řádků v nesousedících tabulkách?

Odpověď: Funkce Untangle Row Bookmarks, jak je uvedena v tomto článku, je navržena tak, aby rozmotala záložky řádků v sousedních tabulkách. K rozuzlení záložek řádků v nesousedících tabulkách mohou být nutné další úpravy kódu v závislosti na struktuře dokumentu.

#### Otázka: Jaké další manipulace mohu provádět se záložkami řádků, jakmile jsou rozbaleny?

Odpověď: Jakmile jsou záložky řádků rozbaleny, můžete podle potřeby provádět různé manipulace. To může zahrnovat úpravy, mazání nebo přidávání obsahu do řádků označených záložkou. S řádkovými záložkami zacházejte opatrně, abyste předešli nechtěnému dopadu na zbytek dokumentu.