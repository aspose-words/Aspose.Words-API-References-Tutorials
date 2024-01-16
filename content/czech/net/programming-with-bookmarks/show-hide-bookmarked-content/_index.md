---
title: Zobrazit skrýt obsah označený záložkou v dokumentu aplikace Word
linktitle: Zobrazit skrýt obsah označený záložkou v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zobrazit nebo skrýt obsah záložek v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

tomto článku prozkoumáme výše uvedený zdrojový kód C#, abychom pochopili, jak používat funkci Zobrazit skrýt obsah se záložkami v knihovně Aspose.Words for .NET. Tato funkce umožňuje zobrazit nebo skrýt obsah záložky v dokumentu aplikace Word na základě konkrétní podmínky při slučování dat.

## Předpoklady

- Základní znalost jazyka C#.
- Vývojové prostředí .NET s nainstalovanou knihovnou Aspose.Words.

## Krok 1: Získání záložky

 Používáme`Bookmarks` vlastnost rozsahu dokumentu, abychom získali konkrétní záložku, na které chceme zobrazit nebo skrýt obsah:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Krok 2: Vložení slučovacích polí

 Používáme nástroj pro tvorbu dokumentů`DocumentBuilder` pro vložení nezbytných slučovacích polí. Tato slučovací pole nastaví podmínku pro zobrazení nebo skrytí obsahu záložky v závislosti na hodnotě`showHide` proměnná:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Krok 3: Přesunutí obsahu záložky

Procházíme obsah záložky a posouváme ji tak, aby se objevila

isse před záložkou. To bude ovládat zobrazení nebo skrytí obsahu na základě zadané podmínky:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Krok 4: Přesunutí zbytku obsahu záložky

Zbytek obsahu záložky přesuneme za záložku, přičemž jako bod vložení použijeme koncový uzel záložky:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Krok 5: Provedení sloučení

 Používáme`Execute` způsob dokumentu`s `Sloučení emailů` object to execute the merge using the bookmark name and the value of the `showHide` proměnná:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Příklad zdrojového kódu pro Show Hide Bookmarked Content pomocí Aspose.Words for .NET

Zde je úplný příklad zdrojového kódu, který demonstruje zobrazení nebo skrytí obsahu záložek pomocí Aspose.Words for .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Závěr

V tomto článku jsme prozkoumali zdrojový kód jazyka C#, abychom pochopili, jak používat funkci Zobrazit skrýt obsah se záložkami Aspose.Words for .NET. Postupovali jsme podle podrobného průvodce, jak zobrazit nebo skrýt obsah záložky na základě konkrétní podmínky při slučování dat.

### Časté dotazy pro show skrýt záložkovaný obsah v dokumentu aplikace Word

#### Otázka: Mohu použít stejnou podmínku pro více záložek ve stejném dokumentu?

Odpověď: Ano, stejnou podmínku můžete použít pro více záložek ve stejném dokumentu. Opakujte kroky 2-5 pro každou záložku, upravte název záložky a volitelně hodnotu`showhide` variabilní dle potřeby.

#### Otázka: Jak mohu přidat další podmínky pro zobrazení nebo skrytí obsahu záložek?

 A: Chcete-li přidat další podmínky, můžete použít logické operátory jako např`AND` a`OR` v kódu pro vkládání slučovacích polí v kroku 2. Upravte podmínku v následujícím kódu a přidejte další podmínky:

```csharp
builder. Write("\" = \"true\" ");
```

#### Otázka: Jak mohu odstranit záložku v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li odstranit záložku v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete použít`Remove` metoda z`Bookmarks` sbírka rozsahu dokumentů. Zde je ukázkový kód pro smazání konkrétní záložky:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Otázka: Je knihovna Aspose.Words zdarma?

 A: Knihovna Aspose.Words je komerční knihovna a pro použití ve vašich projektech vyžaduje platnou licenci. Můžeš zkontrolovat[Aspose.Words for .NET API odkazy](https://reference.aspose.com/words/net/) se dozvíte více o možnostech licencování a cenách.

#### Otázka: Jsou k dispozici další knihovny pro zpracování textu s dokumenty Word v .NET?

Odpověď: Ano, pro textové zpracování s dokumenty Word v .NET jsou k dispozici další knihovny, jako je Open XML SDK a GemBox.Document. Tyto knihovny můžete prozkoumat jako alternativy k Aspose.Words na základě vašich konkrétních potřeb a preferencí.