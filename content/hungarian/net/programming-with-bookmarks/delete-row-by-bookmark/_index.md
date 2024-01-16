---
title: Sor törlése könyvjelzővel a Word dokumentumban
linktitle: Sor törlése könyvjelzővel a Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan törölhet táblázatsort egy adott könyvjelző alapján a Word dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Ebben a cikkben megvizsgáljuk a fenti C# forráskódot, hogy megértsük, hogyan használható a Sor törlése könyvjelzővel funkció az Aspose.Words for .NET könyvtárban. Ez a funkció lehetővé teszi egy táblázatsor törlését egy adott könyvjelző alapján a Word dokumentumban.

## Előfeltételek

- C# nyelv alapismerete.
- .NET fejlesztői környezet telepített Aspose.Words könyvtárral.

## 1. lépés: A könyvjelző lekérése

 Használjuk a`Bookmarks` a dokumentumtartomány tulajdonsága, hogy megkapjuk azt a könyvjelzőt, amelyet a táblázat sorának törléséhez szeretnénk használni:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## 2. lépés: A táblázat sorának törlése

 Használjuk a`GetAncestor` módszer a`Row` írja be a könyvjelző szülőelemét. Ezután használjuk a`Remove` a táblázatsor eltávolításának módja:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Példa a Sor törlése könyvjelzővel forráskódjához az Aspose.Words for .NET használatával

Íme a teljes minta forráskód, amely bemutatja egy táblázatsor törlését egy adott könyvjelző alapján az Aspose.Words for .NET használatával:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Következtetés

Ebben a cikkben megvizsgáltuk a C# forráskódot, hogy megértsük, hogyan használható az Aspose.Words for .NET funkciója. Követtünk egy lépésről lépésre szóló útmutatót a táblázat egy sorának törléséhez a dokumentumban lévő adott könyvjelző alapján.

### GYIK a soronkénti törléshez a Word dokumentumban

#### K: Törölhetek több sort ugyanazzal a könyvjelzővel?

V: Igen, több sort is törölhet ugyanazzal a könyvjelzővel. Azonban kezelnie kell a kódjában található logikát, hogy meghatározza a törölni kívánt sorok számát, és elvégezze a szükséges módosításokat a megadott kódrészleten.

#### K: Mi történik, ha a könyvjelző nem létezik a dokumentumban?

V: Ha a megadott könyvjelző nem létezik a dokumentumban, a kódrészlet null értéket ad vissza a könyvjelző objektumhoz. Ezért ezt a forgatókönyvet kell kezelnie a kódban megfelelő ellenőrzések hozzáadásával, mielőtt megpróbálná törölni a táblázatsort.

#### K: Ingyenesen használható az Aspose.Words könyvtár?

 V: Az Aspose.Words könyvtár egy kereskedelmi célú könyvtár, és a projektekben való használatához érvényes licencre lehet szükség. Meglátogathatja a[Aspose.Words .NET API hivatkozásokhoz](https://reference.aspose.com/words/net/) hogy többet tudjon meg licencelési lehetőségeiről és áraikról.

#### K: Törölhetek sorokat egy táblázatból a Word dokumentum egy adott részében?

V: Igen, törölhet sorokat a Word-dokumentum egy adott szakaszában lévő táblázatból. Módosíthatja a megadott kódrészletet, hogy megcélozzon egy adott szakaszt az adott szakaszon belüli megfelelő tartomány vagy könyvjelző használatával.