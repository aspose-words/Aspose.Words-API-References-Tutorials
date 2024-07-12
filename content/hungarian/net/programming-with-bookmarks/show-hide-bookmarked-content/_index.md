---
title: Könyvjelzővel ellátott tartalom elrejtése a Word-dokumentumban
linktitle: Könyvjelzővel ellátott tartalom elrejtése a Word-dokumentumban
second_title: Aspose.Words Document Processing API
description: Ebből az átfogó, lépésenkénti útmutatóból megtudhatja, hogyan jeleníthet meg vagy rejthet el dinamikusan könyvjelzőkkel ellátott tartalmakat Word-dokumentumokban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Bevezetés

Halihó! Szerette volna valaha is szabályozni bizonyos tartalom láthatóságát egy Word-dokumentumban bizonyos feltételek alapján? Az Aspose.Words for .NET segítségével dinamikusan megjelenítheti vagy elrejtheti a könyvjelzővel ellátott tartalmakat, mindössze néhány sornyi kóddal. Ebben az oktatóanyagban lépésről lépésre végigvezetem a folyamaton, biztosítva, hogy megértse a kód minden részét. A végére profi lesz a Word-dokumentumok könyvjelzőinek kezelésében. Kezdjük el!

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjünk meg arról, hogy mindennel rendelkezik, amire szüksége van:

1. Alapvető C# ismerete: Kényelmesnek kell lennie a C# szintaxisával és fogalmaival.
2.  Aspose.Words for .NET: Töltse le[itt](https://releases.aspose.com/words/net/) . Ha még nem áll készen a vásárlásra, kezdheti a[ingyenes próbaverzió](https://releases.aspose.com/).
3. Visual Studio: Bármelyik legújabb verzió működik, de a legújabb verzió használata javasolt.
4. .NET-keretrendszer: Győződjön meg arról, hogy telepítve van a számítógépén.

Készen áll az indulásra? Nagy! Kezdjük a szükséges névterek importálásával.

## Névterek importálása

Az Aspose.Words for .NET használatához importálnunk kell a szükséges névtereket. Ez a lépés biztosítja, hogy hozzáférjünk az összes használt osztályhoz és metódushoz.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Ezek a névterek kulcsfontosságúak a Word-dokumentumokkal való munkavégzéshez és a tartalom kezeléséhez.

## 1. lépés: A dokumentum beállítása

Először is hozzunk létre egy új Word dokumentumot és egy dokumentumkészítőt. A dokumentumkészítő segítségével könnyen hozzáadhatunk és kezelhetünk tartalmat a dokumentumon belül.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ebben a lépésben inicializálunk egy új dokumentumot és egy dokumentumkészítőt. Ez beállítja környezetünket a további műveletekhez.

## 2. lépés: Könyvjelzővel ellátott tartalom hozzáadása

Ezután hozzáadunk némi tartalmat a dokumentumhoz, és könyvjelzőt hozunk létre körülötte. Ez a könyvjelző segít a tartalom azonosításában és kezelésében.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Itt a könyvjelzővel ellátott tartalom előtt és után szöveget adunk hozzá. A`StartBookmark`és`EndBookmark` metódusok határozzák meg a könyvjelző határait.

## 3. lépés: Feltételes mező beszúrása

könyvjelzővel ellátott tartalom láthatóságának szabályozásához feltételes mezőt használunk. Ez a mező ellenőriz egy feltételt, és ennek megfelelően megjeleníti vagy elrejti a tartalmat.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

Ebben a lépésben beszúrunk egy IF mezőt, amely ellenőrzi a könyvjelző értékét. Ha az érték "true", a "Látható" jelenik meg; ellenkező esetben a "Rejtett" felirat jelenik meg.

## 4. lépés: Csomópontok átrendezése

Ezután át kell rendeznünk a csomópontokat, hogy biztosítsuk a feltételes logika helyes alkalmazását a könyvjelzővel ellátott tartalomra.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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
```

Itt mozgatjuk a csomópontokat, hogy megbizonyosodjunk arról, hogy a feltétel megfelelően lefedi a könyvjelzővel ellátott tartalmat.

## 5. lépés: Körlevél végrehajtása

Végül egy körözést hajtunk végre, hogy beállítsuk a könyvjelző értékét, és meghatározzuk, hogy a tartalom megjelenjen-e vagy elrejtve.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Ez a lépés a könyvjelző értékét "true"-ra állítja, ami a tartalom láthatóvá válik az állapotunk alapján.

## 6. lépés: A dokumentum mentése

Az összes manipuláció után az utolsó lépés a módosított dokumentum mentése.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Itt elmentjük a dokumentumot egy leíró fájlnévvel, hogy jelezzük a változásokat.

## Következtetés

 És ez az! Sikeresen megtanulta, hogyan jeleníthet meg vagy rejthet el könyvjelzővel ellátott tartalmat egy Word-dokumentumban az Aspose.Words for .NET segítségével. Ez az oktatóanyag dokumentum létrehozását, könyvjelzők hozzáadását, feltételes mezők beszúrását, csomópontok átrendezését és körlevél-egyesítés végrehajtását tárgyalta. Az Aspose.Words rengeteg funkciót kínál, ezért ne habozzon felfedezni[API dokumentáció](https://reference.aspose.com/words/net/) fejlettebb képességekért.

## GYIK

### 1. Mi az Aspose.Words for .NET?

Az Aspose.Words for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára Word-dokumentumok programozott létrehozását, módosítását és konvertálását. Széles körben használják dokumentumautomatizálási feladatokhoz.

### 2. Használhatom ingyenesen az Aspose.Words for .NET-et?

 Kipróbálhatja az Aspose.Words for .NET-et a[ingyenes próbaverzió](https://releases.aspose.com/). Hosszú távú használathoz licencet kell vásárolnia.

### 3. Hogyan módosíthatom a könyvjelző egyéb tulajdonságait?

 Az Aspose.Words lehetővé teszi a könyvjelző különféle tulajdonságainak, például a szövegének és a helyének kezelését. Utal[API dokumentáció](https://reference.aspose.com/words/net/) részletes utasításokért.

### 4. Hogyan kaphatok támogatást az Aspose.Words for .NET-hez?

Támogatást kaphat, ha ellátogat a[Aspose támogatási fórum](https://forum.aspose.com/c/words/8).

### 5. Az Aspose.Words for .NET segítségével manipulálhatok más típusú tartalmakat?

Igen, az Aspose.Words for .NET támogatja a tartalomkezelés különféle típusait, beleértve a szöveget, képeket, táblázatokat és egyebeket.