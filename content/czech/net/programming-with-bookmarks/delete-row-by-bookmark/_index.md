---
title: Odstranit řádek podle záložky v dokumentu aplikace Word
linktitle: Odstranit řádek podle záložky v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak odstranit řádek tabulky na základě konkrétní záložky v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/delete-row-by-bookmark/
---

V tomto článku prozkoumáme výše uvedený zdrojový kód C#, abychom pochopili, jak používat funkci Delete Row By Bookmark v knihovně Aspose.Words for .NET. Tato funkce umožňuje odstranit řádek tabulky na základě konkrétní záložky v dokumentu aplikace Word.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Získání záložky

 Používáme`Bookmarks` vlastnost rozsahu dokumentů, abychom získali konkrétní záložku, kterou chceme použít k odstranění řádku tabulky:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Krok 2: Odstranění řádku tabulky

 Používáme`GetAncestor` způsob, jak získat`Row` zadejte nadřazený prvek záložky. Dále použijeme`Remove` způsob odstranění řádku tabulky:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Příklad zdrojového kódu pro Delete Row By Bookmark pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje odstranění řádku tabulky na základě konkrétní záložky pomocí Aspose.Words for .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Delete Row By Bookmark Aspose.Words for .NET. Postupovali jsme podle podrobného průvodce, jak odstranit řádek tabulky na základě konkrétní záložky v dokumentu.

### Časté dotazy k odstranění řádku podle záložky v dokumentu aplikace Word

#### Otázka: Mohu odstranit více řádků pomocí stejné záložky?

Odpověď: Ano, pomocí stejné záložky můžete odstranit více řádků. Chcete-li však určit počet řádků, které se mají odstranit, a provést potřebné úpravy poskytnutého fragmentu kódu, musíte ve svém kódu zacházet s logikou.

#### Otázka: Co se stane, když záložka v dokumentu neexistuje?

Odpověď: Pokud zadaná záložka v dokumentu neexistuje, fragment kódu vrátí hodnotu null pro objekt záložky. Proto musíte tento scénář v kódu zpracovat přidáním příslušných kontrol před pokusem o odstranění řádku tabulky.

#### Otázka: Je knihovna Aspose.Words zdarma k použití?

 Odpověď: Knihovna Aspose.Words je komerční knihovna a k jejímu použití ve svých projektech můžete potřebovat platnou licenci. Můžete navštívit[Aspose.Words for .NET API odkazy](https://reference.aspose.com/words/net/) se dozvíte více o jejich licenčních možnostech a cenách.

#### Otázka: Mohu odstranit řádky z tabulky v určité části dokumentu aplikace Word?

Odpověď: Ano, můžete odstranit řádky z tabulky v určité části dokumentu aplikace Word. Poskytnutý fragment kódu můžete upravit tak, aby cílil na konkrétní sekci, pomocí příslušného rozsahu nebo záložky v této sekci.