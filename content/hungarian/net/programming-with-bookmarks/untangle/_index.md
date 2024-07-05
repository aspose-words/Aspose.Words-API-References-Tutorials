---
title: Kibontani a Word dokumentumban
linktitle: Kibontani a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Tanulja meg, hogyan bonthatja ki a Word dokumentumba ágyazott könyvjelzőit a szomszédos táblázatsorokban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/untangle/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használható az Untangle függvény az Aspose.Words for .NET könyvtárban. Ez a függvény feloldja a szomszédos táblázatsorokban lévő beágyazott könyvjelzőket.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: Tallózás a dokumentumok könyvjelzői között

Foreach ciklust használunk a dokumentumban található összes könyvjelző áthaladásához:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Kód a könyvjelzők kezeléséhez itt
}
```

## 2. lépés: Szülősorok lekérése a könyvjelzőkből

 Használjuk a`GetAncestor` módszerek a könyvjelző kezdő és záró csomópontjainak szülősorainak lekéréséhez:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## 3. lépés: Oldja ki a beágyazott könyvjelzőket

Ha mindkét szülősor megtalálható, és a könyvjelző szomszédos sorokban kezdődik és végződik, akkor a könyvjelző végcsomópontját a felső sor utolsó cellája utolsó bekezdésének végére mozgatjuk:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Példa forráskód az Untangle programhoz az Aspose.Words for .NET használatával

Íme a teljes forráskód példa a beágyazott könyvjelzők kibontásához az Aspose.Words for .NET használatával:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// A könyvjelző és a könyvjelző végcsomópont szülősorának lekérése.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Ha mindkét sor rendben van, és a könyvjelző eleje és vége a szomszédos sorokban található,
		// mozgassa a könyvjelző végcsomópontját a felső sor utolsó cellájának utolsó bekezdésének végére.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words .NET-hez Untangle funkciója. Követtünk egy lépésről lépésre szóló útmutatót a szomszédos táblázatsorokban lévő beágyazott könyvjelzők kibontásához.

### GYIK

#### K: Az Untangle funkció csak a szomszédos táblázatsorokban lévő beágyazott könyvjelzőkkel működik?

V: Igen, a Kibontás funkció kifejezetten a szomszédos táblázatsorokban található beágyazott könyvjelzők kibontására szolgál. Ha a könyvjelzők nincsenek szomszédos sorokban, ez a funkció nem használható.

#### K: Hogyan azonosíthatom be a beágyazott könyvjelzőket a Word-dokumentumban?

V: A beágyazott könyvjelzőket úgy azonosíthatja, hogy végigpörgeti a könyvjelzőket a dokumentumban, és megnézi, hogy a kezdő és a záró könyvjelző a szomszédos táblázatsorokban található-e. A funkció megvalósításához a cikkben található forráskódot használhatja kiindulási pontként.

#### K: Az Unscramble funkció módosítja az eredeti dokumentum tartalmát?

V: Igen, a Untangle funkció úgy módosítja az eredeti dokumentumot, hogy a könyvjelző végcsomópontját a felső sor utolsó cellája utolsó bekezdésének végére mozgatja. A funkció alkalmazása előtt mindenképpen mentsen biztonsági másolatot a dokumentumról.

#### K: Hogyan távolíthatom el a beágyazott könyvjelzőket más típusú dokumentumelemekben, például szakaszokban vagy bekezdésekben?

V: A jelen cikkben bemutatott Untangle funkció kifejezetten a szomszédos táblázatsorokban lévő beágyazott könyvjelzők kibontására szolgál. Ha más dokumentumelemekben szeretné szétválasztani a beágyazott könyvjelzőket, akkor ennek megfelelően módosítania kell a kódot, és megfelelő módszereket kell használnia a kívánt elemek eléréséhez.

#### K: Vannak más módszerek a beágyazott könyvjelzők feloldására egy Word-dokumentumban az Aspose.Words for .NET használatával?

 V: Az ebben a cikkben bemutatott módszer egy általános módszer a szomszédos táblázatsorokban lévő beágyazott könyvjelzők kibontására. A projekt konkrét igényeitől függően azonban létezhetnek más megközelítések vagy technikák is. Megnézheti a[Aspose.Words .NET API hivatkozásokhoz](https://reference.aspose.com/words/net/) az elérhető funkciók további felfedezéséhez.