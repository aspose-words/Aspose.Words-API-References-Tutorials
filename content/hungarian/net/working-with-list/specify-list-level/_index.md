---
title: Adja meg a lista szintjét
linktitle: Adja meg a lista szintjét
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhatja meg a listaszintet egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-list/specify-list-level/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan adhatja meg a lista szintjét egy Word-dokumentumban az Aspose.Words for .NET használatával. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és konfigurálva van a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A dokumentum és a dokumentumgenerátor létrehozása

Először hozzon létre egy új dokumentumot és egy kapcsolódó dokumentumgenerátort:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Számozott lista létrehozása és alkalmazása

Ezután hozzon létre egy számozott listát a Microsoft Word egyik listasablonja alapján, és alkalmazza azt az aktuális bekezdésre a dokumentumkészítőben:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## 3. lépés: Lista szintű specifikáció

 Használja a dokumentumkészítőt`ListLevelNumber` tulajdonság a lista szintjének megadásához és szöveg hozzáadásához a bekezdéshez:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Ismételje meg ezeket a lépéseket a listaszintek megadásához és szöveg hozzáadásához az egyes szinteken.

## 4. lépés: Felsorolásos lista létrehozása és alkalmazása

A Microsoft Word listasablonjainak egyikével is létrehozhat és alkalmazhat felsorolásjeles listát:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## 5. lépés: Szöveg hozzáadása a felsorolásjeles listaszintekhez

 Használja a`ListLevelNumber` tulajdonság újra a felsorolásjeles lista szintjének megadásához és szöveg hozzáadásához:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## 6. lépés: Állítsa le a lista formázását

 A lista formázásának leállításához állítsa be`null` hoz`List` dokumentumgenerátor tulajdonsága:

```csharp
builder. ListFormat. List = null;
```

## 7. lépés: Mentse el a módosított dokumentumot

Mentse el a módosított dokumentumot:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Így ! Sikeresen megadta a listaszintet egy Word-dokumentumban az Aspose.Words for .NET használatával.

### Minta forráskód a listaszint meghatározásához

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Hozzon létre egy számozott listát az egyik Microsoft Word listasablon alapján
//és alkalmazza a dokumentumkészítő aktuális bekezdésére.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Kilenc szint található ebben a listában, próbáljuk ki mindegyiket.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Hozzon létre egy felsorolásjeles listát a Microsoft Word listasablonjainak egyike alapján
//és alkalmazza a dokumentumkészítő aktuális bekezdésére.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Ezzel leállíthatja a lista formázását.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### GYIK

#### K: Hogyan adhatok meg listaszintet az Aspose.Words-ben?

 V: Az Aspose.Words listaszintjének megadásához létre kell hoznia egy példányt a`List` osztályt, és adj neki egy számozott listát. Ezután használhatja a`Paragraph.ListFormat.ListLevelNumber` tulajdonság az egyes listaelemek szintjének megadásához. Ezt a listát a dokumentum egy részéhez társíthatja, így a listaelemek a kívánt szinttel rendelkeznek.

#### K: Megváltoztatható az Aspose.Words listaelemeinek számozási formátuma?

 V: Igen, módosíthatja az Aspose.Words listaelemeinek számozási formátumát. A`ListLevel` osztály több tulajdonságot kínál erre, mint pl`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, stb. Ezekkel a tulajdonságokkal beállíthatja a listaelemek számozási formátumát, például arab számokat, római számokat, betűket stb.

#### K: Hozzáadhatok további szinteket az Aspose.Words számozott listájához?

 V: Igen, lehetséges további szinteket hozzáadni az Aspose.Words számozott listájához. A`ListLevel`osztály lehetővé teszi a formázási tulajdonságok beállítását a lista minden szintjéhez. Beállíthat olyan beállításokat, mint az előtag, utótag, igazítás, behúzás stb. Ez lehetővé teszi több szintű hierarchiával rendelkező listák létrehozását.


