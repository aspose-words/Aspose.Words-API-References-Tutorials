---
title: Mezők konvertálása a testben
linktitle: Mezők konvertálása a testben
second_title: Aspose.Words Document Processing API
description: Tanulja meg az Aspose.Words for .NET használatával az oldalmezőket szöveggé alakítani egy Word-dokumentum törzsében.
type: docs
weight: 10
url: /hu/net/working-with-fields/convert-fields-in-body/
---

Ebben a lépésenkénti oktatóanyagban végigvezetjük, hogyan használhatja az Aspose.Words for .NET ConvertFieldsInBody funkcióját a mellékelt C# forráskód használatával. Ez a funkció lehetővé teszi, hogy a dokumentum törzsében lévő mezőket egyszerű szöveggé alakítsa, így a dokumentumok könnyebben feldolgozhatók. Kövesse az alábbi lépéseket a funkció hatékony használatához.

## 1. lépés: Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.Words for .NET programot, és rendelkezik-e feldolgozásra kész dokumentummal. Győződjön meg arról is, hogy rendelkezik a dokumentumok könyvtárának elérési útjával.

## 2. lépés: Töltse be a dokumentumot

Először deklaráljon egy változót a dokumentumkönyvtár elérési útjához, majd ezzel a változóval inicializáljon egy dokumentumobjektumot a megadott dokumentumból. Példánkban a dokumentum neve "Linked fields.docx".

```csharp
// A dokumentumkönyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Linked fields.docx");
```

## 3. lépés: Alakítsa át az oldalmezőket egyszerű szöveggé

 Most, hogy a dokumentum betöltődött, továbbléphetünk az átalakítási lépésekre. Az oldalmezők egyszerű szöveggé alakításához az első szakasz törzsében használhatja a`Range.Fields` metódussal, hogy a megadott tartományban lévő összes mezőt megkapja, majd kiszűrje a típusú mezőket`FieldType.FieldPage` . Ezután használhatja a`ForEach` metódussal végigpörgeti az egyes mezőket, és meghívja a`Unlink()` egyszerű szöveggé konvertálási módszer.

```csharp
// Adja meg a megfelelő paramétereket az oldalmezők egyszerű szöveggé alakításához az első szakasz törzsében.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## 4. lépés: Mentse el a módosított dokumentumot

Miután az oldalmezőket sima szöveggé alakította, a módosított dokumentumot a következővel mentheti`Save()` metódust, és megadja a kimeneti fájl elérési útját és nevét. Példánkban "WorkingWithFields.ConvertFieldsInBody.docx" néven mentjük el.

```csharp
// Mentse el a módosított dokumentumot
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Példa forráskódra a törzsben lévő mezők konvertálásához az Aspose.Words for .NET segítségével

Íme a teljes forráskód példa a mezők törzsté konvertálására az Aspose.Words for .NET használatával:

```csharp
// A dokumentumkönyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Linked fields.docx");

// Adja meg a megfelelő paramétereket az oldalmezők egyszerű szöveggé alakításához az első szakasz törzsében.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### GYIK

#### K: Az Aspose.Words kompatibilis a Microsoft Word különböző verzióival?

V: Igen, az Aspose.Words kompatibilis a Microsoft Word különféle verzióival, beleértve a Word 2003-at, a Word 2007-et, a Word 2010-et, a Word 2013-at, a Word 2016-ot és a Word 2019-et.

#### K: Az Aspose.Word képes kezelni az összetett mezőstruktúrákat?

V: Abszolút! Az Aspose.Words kiterjedt támogatást nyújt összetett mezőstruktúrákhoz, beleértve a beágyazott mezőket, számításokat és feltételes kifejezéseket. A hatékony API segítségével bármilyen típusú mezőszerkezettel dolgozhat.

#### K: Az Aspose.Words támogatja a helyszíni frissítési műveleteket?

V: Igen, az Aspose.Words lehetővé teszi a mezők programozott frissítését. Az API segítségével egyszerűen frissítheti a mezőértékeket, frissítheti a számításokat, és végrehajthat más, mezővel kapcsolatos műveleteket.

#### K: Átalakíthatom a mezőket egyszerű szöveggé az Aspose.Words használatával?

V: Természetesen! Az Aspose.Words módszereket biztosít a mezők egyszerű szöveggé alakítására. Ez akkor lehet hasznos, ha a tartalmat mezőhöz kapcsolódó formázás vagy funkció nélkül kell kibontani.

#### K: Lehetséges-e dinamikus mezőket tartalmazó Word-dokumentumok generálása az Aspose.Words használatával?

V: Abszolút! Az Aspose.Words robusztus szolgáltatásokat kínál dinamikus mezőket tartalmazó Word-dokumentumok létrehozásához. Előre definiált mezőket tartalmazó sablonokat hozhat létre, és dinamikusan töltheti fel adatokkal, így rugalmas és hatékony dokumentumgenerálási megoldást kínál.