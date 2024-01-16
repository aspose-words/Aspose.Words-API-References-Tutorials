---
title: Frissítse a könyvjelzők adatait a Word dokumentumban
linktitle: Frissítse a könyvjelzők adatait
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre ismerteti az Aspose.Words könyvjelzők adatfrissítésének C# forráskódját a Word dokumentum funkciójában a .NET-hez.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/update-bookmark-data/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük az Aspose.Words for .NET könyvjelzőadatainak frissítése Word dokumentumban funkciójának megértéséhez és megvalósításához. Ezzel a funkcióval frissítheti a Word-dokumentumban lévő könyvjelzők tartalmát és tulajdonságait C# forráskód használatával.

## Követelmények

Mielőtt folytatná az oktatóanyagot, győződjön meg arról, hogy megfelel a következő követelményeknek:

- Aspose.Words for .NET könyvtár telepítve
- C# programozási nyelv alapismerete
- Visual Studio vagy bármely más kompatibilis IDE

## 1. lépés: Töltse be a dokumentumot

Ebben a lépésben betöltjük azt a Word dokumentumot, amely a frissíteni kívánt könyvjelzőket tartalmazza. Feltéve, hogy a dokumentumot egy adott könyvtárban tárolja, használja a következő kódot a dokumentum betöltéséhez:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges könyvtár elérési útjával, ahol a dokumentum található.

## 2. lépés: Nyissa meg a könyvjelzőt

A könyvjelzők adatainak frissítéséhez először el kell érnünk az adott könyvjelzőt a dokumentumon belül. Minden könyvjelzőhöz egyedi név tartozik. Használja a következő kódot a "MyBookmark1" nevű könyvjelző eléréséhez:

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

Győződjön meg arról, hogy a könyvjelző neve megegyezik a dokumentumban szereplővel. Igény szerint módosíthatja.

## 3. lépés: Frissítse a könyvjelző tulajdonságait és tartalmát

Miután elérte a könyvjelzőt, frissítheti annak tulajdonságait és tartalmát. A következő kódrészletben frissítjük a könyvjelző nevét és szövegét:

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

Igényei szerint testreszabhatja a könyvjelző nevét és az új szöveget. A fenti kód átnevezi a könyvjelzőt "RenamedBookmark"-ra, és frissíti a szöveges tartalmat.

## 4. lépés: Mentse el a frissített dokumentumot

A könyvjelző adatainak frissítése után el kell mentenie a módosított dokumentumot. A dokumentum mentéséhez használja a következő kódot:

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

Ez a kód elmenti a módosított dokumentumot "UpdatedDocument.docx" néven ugyanabba a könyvtárba, mint az eredeti dokumentum.

### Példa forráskód a könyvjelzők adatainak frissítéséhez az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges könyvtár elérési útjával, ahol a dokumentum található.

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan frissítheti a könyvjelzők adatait az Aspose.Words for .NET használatával. Az oktatóanyag lépésenkénti útmutatóját követve most már beépítheti ezt a funkciót C#-alkalmazásaiba, és programozottan kezelheti a Word-dokumentumok könyvjelzőit.

### GYIK a könyvjelzők adatainak frissítéséhez a Word dokumentumban

#### K: A könyvjelzőadatok frissítése funkció csak a Word dokumentumokban lévő könyvjelzőkkel működik?

V: Igen, a Könyvjelzőadatok frissítése funkció kifejezetten a Word dokumentumok könyvjelzőihez készült. Lehetővé teszi a könyvjelzők tartalmának és tulajdonságainak frissítését egy Word-dokumentumban.

#### K: Frissíthetem a könyvjelzők egyéb tulajdonságait a szövegen kívül?

 V: Igen, a szövegen kívül a könyvjelző egyéb tulajdonságait is frissítheti, például a könyvjelző nevét, a könyvjelző hatókörét stb. Használja a megfelelő tulajdonságokat a`Bookmark` objektumot a kívánt tulajdonságok frissítéséhez.

#### K: Frissíthetek több könyvjelzőt ugyanabban a dokumentumban?

V: Igen, több könyvjelzőt is frissíthet ugyanabban a dokumentumban, ha megismétli a hozzáférési és frissítési lépéseket minden könyvjelzőhöz. Ügyeljen arra, hogy minden frissíteni kívánt könyvjelzőhöz egyedi könyvjelzőnevet használjon.

#### K: A könyvjelzőadatok frissítése funkció módosítja az eredeti dokumentumot?

V: Igen, a könyvjelzőadatok frissítési funkciója módosítja az eredeti dokumentumot a könyvjelző tulajdonságainak és tartalmának frissítésével. A funkció alkalmazása előtt mindenképpen mentse el az eredeti dokumentum másolatát.