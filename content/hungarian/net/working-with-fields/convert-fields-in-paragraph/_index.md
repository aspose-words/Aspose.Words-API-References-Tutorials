---
title: Mezők konvertálása a bekezdésben
linktitle: Mezők konvertálása a bekezdésben
second_title: Aspose.Words Document Processing API
description: Konvertálja az IF mezőket egyszerű szöveggé egy bekezdésben az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/convert-fields-in-paragraph/
---

Íme egy oktatóanyag, amely bemutatja, hogyan használható a Mezők bekezdésekké alakítása funkció az Aspose.Words for .NET-ben. Ez a kód a dokumentum utolsó bekezdésében található összes IF típusú mezőt egyszerű szöveggé konvertálja. Kövesse az alábbi lépéseket a kód megértéséhez és futtatásához.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.Words for .NET programot, és állítsa be a fejlesztői környezetet.

## 1. lépés: Referenciák importálása

Az Aspose.Words projektben való használatához hozzá kell adnia a szükséges hivatkozásokat. Győződjön meg arról, hogy a projektben hozzáadott egy hivatkozást az Aspose.Words könyvtárra.

## 2. lépés: A dokumentum betöltése

A mezők konvertálása előtt be kell töltenie a konvertálandó mezőket tartalmazó dokumentumot. Ügyeljen arra, hogy a dokumentumot tartalmazó könyvtár helyes elérési útját adja meg. Így töltheti fel a dokumentumot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Cserélje le a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjával.

## 3. lépés: Mezők átalakítása szöveggé

Most, hogy a dokumentum betöltődött, folytathatjuk a típusmezők egyszerű szöveggé alakítását. Ebben a példában csak a dokumentum utolsó bekezdésében található mezőket célozzuk meg. Íme a kód, amely végrehajtja az átalakítást:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Ez a kód a LINQ metódusok kombinációját használja a dokumentum utolsó bekezdésében lévő mezők kiszűrésére, majd egyszerű szöveggé alakítja azokat a`Unlink()` módszer.

## 4. lépés: Mentse el a módosított dokumentumot

 A mezők átalakítása után elmentheti a módosított dokumentumot. Használja a`Save()` módszer erre. Íme egy példa:

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a biztonsági mentéshez.

### Példa forráskódra a bekezdésben lévő mezők konvertálásához az Aspose.Words használatával .NET-hez

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot.
Document doc = new Document(dataDir + "Linked fields.docx");

// Konvertálja az IF mezőket egyszerű szöveggé a dokumentum utolsó bekezdésében.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Mentse el a módosított dokumentumot.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### GYIK

#### K: Mi az Aspose.Words konverziós mezője?

V: Az Aspose.Words konverziós mezője egy olyan típusú mező, amely egy értéket vagy kifejezést más formátumba vagy adattípusba konvertál. Használhat például egy konverziós mezőt, hogy egy dátumot egy adott formátumba, egy számot szöveggé alakítson, vagy más típusú konverziókat hajtson végre.

#### K: Hogyan lehet konverziós mezőt beszúrni egy bekezdésbe az Aspose.Words használatával?

V: Ha konverziós mezőt szeretne beszúrni egy bekezdésbe az Aspose.Words használatával, kövesse az alábbi lépéseket:

1. Importálja a Document osztályt az Aspose.Words névtérből.
2. Hozzon létre egy példányt a dokumentumból a meglévő dokumentum betöltésével.
3. Szerezze meg azt a bekezdést, ahová be szeretné szúrni a konverziós mezőt.
4. Használja az InsertField metódust a konverziós mező beillesztéséhez a megfelelő szintaxissal.

#### K: Milyen konverziós formátumokat támogat az Aspose.Words?

V: Az Aspose.Words a mezőkben a konverziós formátumok széles skáláját támogatja, beleértve a dátumformátumokat, számformátumokat, szövegformátumokat, pénznemformátumokat, százalékos formátumokat stb. Az elérhető konverziós formátumok teljes listáját az Aspose.Words dokumentációban találja.

#### K: Hogyan lehet frissíteni egy konverziós mezőt egy Word-dokumentumban az Aspose.Words segítségével?

V: A Word-dokumentum konverziós mezőjének Aspose.Words segítségével történő frissítéséhez használhatja az UpdateFields metódust. Ez a módszer végigfut a dokumentumon, és frissíti az összes mezőt, beleértve a konverziós mezőket is, és újraszámolja az értékeket az aktuális adatok alapján.