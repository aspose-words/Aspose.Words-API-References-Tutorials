---
title: Oldja ki a sor könyvjelzőit a Word dokumentumban
linktitle: Oldja ki a sor könyvjelzőit a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan bonthatja ki a beágyazott soros könyvjelzőket a Word dokumentumban, és távolíthat el bizonyos sorokat anélkül, hogy ez más könyvjelzőket érintene.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használható az Untangle Row Bookmarks funkció az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi, hogy a sorok könyvjelzőinek végeit egy sorba helyezze a könyvjelzők kezdetével.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: A dokumentum betöltése

 Használjuk a`Document` osztály a meglévő dokumentum fájlból való betöltéséhez:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## 2. lépés: Oldja fel a sor könyvjelzőit

 Használjuk a`Untangle` funkció a könyvjelzők sorokból való kibontásához. Ez a funkció azt az egyéni feladatot hajtja végre, hogy a könyvjelző sorok végét ugyanabba a sorba helyezi, ahol a könyvjelző kezdődik:

```csharp
Untangle(doc);
```

## 3. lépés: Törölje soronként a könyvjelzőt

 Használjuk a`DeleteRowByBookmark` függvény egy adott sor törléséhez a könyvjelzője alapján:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## 4. lépés: Ellenőrizze a többi könyvjelző sértetlenségét

Ellenőrizzük, hogy a többi könyvjelző nem sérült-e, és ellenőrizzük, hogy a könyvjelző vége még mindig jelen van-e:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Példa forráskód a soros könyvjelzők kibontásához az Aspose.Words for .NET használatával

Íme a teljes minta forráskód, amellyel az Aspose.Words for .NET segítségével kibonthatja a könyvjelzőket a sorokból:


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Ez azt az egyéni feladatot hajtja végre, hogy a sor könyvjelző végeit ugyanabba a sorba helyezi, ahol a könyvjelző kezdődik.
	Untangle(doc);

	// Mostantól egyszerűen törölhetünk sorokat egy könyvjelzővel anélkül, hogy a többi sor könyvjelzőjét károsítanánk.
	DeleteRowByBookmark(doc, "ROW2");

	// Ez csak annak ellenőrzésére szolgál, hogy a másik könyvjelző nem sérült-e.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### A forráskód kibontása
```csharp

private void Untangle(Document doc)
        {
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
        }

```

#### DeleteRowByBookmark forráskód
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használhatjuk az Aspose.Words .NET-hez tartozó Sorkönyvjelzők feloldása funkcióját. Követtünk egy lépésről lépésre szóló útmutatót a sor könyvjelzőinek feloldásához és egy adott sor törléséhez a többi könyvjelző károsodása nélkül.

### GYIK a sorkönyvjelzők Word dokumentumban történő kibontásához

#### K: Az Unscramble Row Bookmarks csak a táblázatokban lévő sorkönyvjelzőkkel működik?

V: Igen, a Sorkönyvjelzők feloldása funkció kifejezetten a táblázatokban található sorkönyvjelzők kibontására szolgál. Ez a funkció használható soros könyvjelzők feldolgozására tömbökben, és biztosíthatja, hogy a könyvjelző vége ugyanabban a sorban legyen, mint a könyvjelzők kezdete.

#### K: Módosítja az Unscramble Line Bookmarks funkció az eredeti dokumentum tartalmát?

V: Igen, a sorkönyvjelzők feloldása funkció úgy módosítja az eredeti dokumentumot, hogy a könyvjelzők sorvégeit elmozdítja, hogy azok ugyanabba a sorba kerüljenek, mint a könyvjelzők eleje. A funkció alkalmazása előtt mindenképpen mentsen biztonsági másolatot a dokumentumról.

#### K: Hogyan azonosíthatom be a soros könyvjelzőket a Word-dokumentumban?

V: A sorkönyvjelzőket általában táblázatokban használják meghatározott szakaszok megjelölésére. A sor könyvjelzőit úgy azonosíthatja, hogy a dokumentumban lévő könyvjelzők között böngészik, és ellenőrzi, hogy a könyvjelzők a táblázat soraiban vannak-e.

#### K: Lehetséges-e kibontani a sorkönyvjelzőket a nem szomszédos táblázatokban?

V: Az ebben a cikkben bemutatott Sorkönyvjelzők feloldása funkció a szomszédos táblázatok sorkönyvjelzőinek kibontására szolgál. A nem szomszédos táblázatokban lévő sorkönyvjelzők szétválasztásához a dokumentum szerkezetétől függően további módosításokra lehet szükség a kódban.

#### K: Milyen egyéb manipulációkat hajthatok végre a soros könyvjelzőkkel, miután azokat feloldották?

V: A sorkönyvjelzők feloldása után szükség szerint különböző manipulációkat hajthat végre. Ez magában foglalhatja a könyvjelzővel ellátott sorok szerkesztését, törlését vagy tartalom hozzáadását. Ügyeljen arra, hogy óvatosan kezelje a soros könyvjelzőket, hogy elkerülje a dokumentum többi részére gyakorolt nem kívánt hatást.