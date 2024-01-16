---
title: Přidat text se záložkou v dokumentu aplikace Word
linktitle: Přidat text se záložkou v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak přidat text ze záložky do dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/append-bookmarked-text/
---

V tomto článku prozkoumáme výše uvedený zdrojový kód C#, abychom porozuměli tomu, jak používat funkci Append Bookmarked Text v knihovně Aspose.Words for .NET. Tato funkce umožňuje přidat text obsažený v konkrétní záložce dokumentu aplikace Word do jiného dokumentu.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Získání odstavců ze záložky

 Než začneme přidávat text záložky, musíme získat odstavce, které obsahují začátek a konec záložky. To lze provést přístupem k`BookmarkStart` a`BookmarkEnd` vlastnosti záložky:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Krok 2: Zkontrolujte nadřazené odstavce

Kontrolujeme, zda mají počáteční a koncové odstavce platné rodiče, tedy zda do odstavce skutečně patří. Pokud ne, vygenerujeme výjimku:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Krok 3: Zkontrolujte rodiče odstavců

Zkontrolujeme, zda začátek a konec odstavce mají stejného rodiče. Pokud ne, znamená to, že odstavce nejsou obsaženy ve stejné sekci nebo dokumentu a vyvoláme výjimku:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Krok 4: Zkopírujte odstavce

Iterujeme uzly (odstavce) od počátečního odstavce ke koncovému odstavci. Pro každý uzel vytvoříme kopii a importujeme ji do kontextu cílového dokumentu:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Příklad zdrojového kódu pro Append Bookmarked Text pomocí Aspose.Words for .NET

Zde je úplný ukázkový zdrojový kód, který demonstruje přidávání textu ze záložky pomocí Aspose.Words pro .NET:

```csharp

	// Toto je odstavec, který obsahuje začátek záložky.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Toto je odstavec, který obsahuje konec záložky.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Omezte se na přiměřeně jednoduchý scénář.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Chceme zkopírovat všechny odstavce od počátečního odstavce až po (včetně) koncového odstavce,
	// proto uzel, u kterého zastavíme, je jeden za koncovým odstavcem.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Tím se vytvoří kopie aktuálního uzlu a importuje se (učiní se platným) v kontextu
		// cílového dokumentu. Import znamená správnou úpravu stylů a identifikátorů seznamu.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód C#, abychom pochopili, jak používat funkci Append Bookmarked Text Aspose.Words for .NET. Postupovali jsme krok za krokem, jak získat odstavce ze záložky, ověřit rodiče a zkopírovat odstavce do jiného dokumentu.

### Nejčastější dotazy pro přidání textu se záložkou do dokumentu aplikace Word

#### Q1: Jaké jsou předpoklady pro použití funkce "Přidat text se záložkami" v Aspose.Words pro .NET?

A: Chcete-li použít funkci "Přidat text se záložkami" v Aspose.Words pro .NET, musíte mít základní znalosti jazyka C#. Potřebujete také vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

#### Q2: Jak získat odstavce, které obsahují začátek a konec záložky v dokumentu aplikace Word?

Odpověď: Chcete-li získat odstavce, které obsahují začátek a konec záložky v dokumentu aplikace Word, můžete získat přístup k`BookmarkStart` a`BookmarkEnd` vlastnosti záložky. Zde je ukázkový kód:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Otázka 3: Co se stane, když počáteční a koncové odstavce nemají platné rodiče?

A: Pokud počáteční a koncové odstavce nemají platné rodiče, tj. ve skutečnosti to nejsou odstavce, bude vyvolána výjimka. Tuto situaci nelze v tuto chvíli zvládnout.
