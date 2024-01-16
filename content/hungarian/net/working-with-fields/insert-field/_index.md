---
title: Mező beszúrása
linktitle: Mező beszúrása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be mezőt Word-dokumentumaiba az Aspose.Words for .NET segítségével. Tegye személyre dokumentumait dinamikus mezőkkel.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-field/
---

Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "Mező beszúrása" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A Document és a DocumentBuilder létrehozása

Kezdjük egy új dokumentum létrehozásával és a DocumentBuilder inicializálásával.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: A mező beillesztése

 Használjuk a`InsertField()` a DocumentBuilder metódusa mező beszúrásához a dokumentumba. Ebben a példában egy összevonási mezőt (MERGEFIELD) szúrunk be "MyFieldName" mezőnévvel és egyesítési formátummal.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Példa a forráskódra az Aspose.Words mező beszúrásához a .NET számára

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozza létre a dokumentumot és a DocumentBuildert.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Helyezze be a mezőt.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

Ebben a példában létrehoztunk egy új dokumentumot, inicializáltunk egy DocumentBuilder-t, majd beszúrtunk egy összevonási mezőt "MyFieldName" mezőnévvel és egyesítési formátummal. A dokumentum ezután meghatározott fájlnévvel kerül mentésre.

Ezzel véget is értünk az Aspose.Words for .NET "Mező beszúrása" funkciójának használatáról szóló útmutatónknak.

### GYIK

#### K: Mi az a mező a Wordben?

V: A Word mezője olyan elem, amely lehetővé teszi dinamikus adatok beszúrását és kezelését a dokumentumban. Változó információk, például dátumok, oldalszámok, táblázatok, matematikai képletek stb. megjelenítésére használható.

#### K: Hogyan lehet beszúrni egy mezőt egy Word dokumentumba?

V: Ha egy mezőt Word-dokumentumba szeretne beszúrni, kövesse az alábbi lépéseket:

1. Vigye a kurzort oda, ahová be szeretné szúrni a mezőt.
2. Lépjen a "Beszúrás" fülre a szalagon.
3. Kattintson a "Mező" gombra a "Szöveg" csoportban a mezők párbeszédpanelének megnyitásához.
4. Válassza ki a beszúrni kívánt mező típusát a legördülő listából.
5. Szükség szerint konfigurálja a mezőbeállításokat.
6. Kattintson az "OK" gombra a mező beillesztéséhez a dokumentumba.

#### K: Melyek a Word leggyakrabban használt mezőtípusai?

V: A Word a mezőtípusok széles választékát kínálja, amelyeket felhasználhat a dokumentumokban. Íme néhány gyakran használt mezőtípus:

- Dátum és idő: megjeleníti az aktuális dátumot és időt.
- Oldalszám: az aktuális oldalszámot jeleníti meg.
- Tartalomjegyzék: automatikusan létrehoz egy tartalomjegyzéket a címek stílusa alapján.
- Számítás: matematikai számításokat végez képletek segítségével.
- Kitöltő szöveg: Véletlenszerű szöveget generál a dokumentum kitöltéséhez.

#### K: Testreszabhatom a mezők megjelenését a Wordben?

V: Igen, testreszabhatja a mezők megjelenését a Wordben a rendelkezésre álló formázási beállítások segítségével. Módosíthatja például a mezőben lévő szöveg betűtípusát, méretét, színét és stílusát. Alkalmazhat formázási effektusokat is, például félkövér, dőlt és aláhúzott.
  