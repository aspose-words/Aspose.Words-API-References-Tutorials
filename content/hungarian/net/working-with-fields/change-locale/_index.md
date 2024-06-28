---
title: Helyszín módosítása
linktitle: Helyszín módosítása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan módosíthatja a dátum- és számformázás területi beállítását a Word-dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-fields/change-locale/
---

Ebben az oktatóanyagban végigvezetjük a Word-dokumentumok nyelv- és területi beállításának megváltoztatásán az Aspose.Words for .NET használatával. A területi beállítás módosításával szabályozhatja a dátumok és számok formázását a körlevél-műveletek során. Ennek eléréséhez megadjuk a szükséges C# forráskódot és lépésről lépésre.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy dokumentumot és a DocumentBuildert
Kezdésként hozzon létre egy példányt a Document osztályból és egy DocumentBuilder objektumból:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Szúrjon be egy mezőt
Ezután szúrjon be egy összevonási mezőt a dokumentumba az InsertField metódussal:

```csharp
builder.InsertField("MERGEFIELD Date");
```

A fenti kódban beszúrunk egy "Dátum" nevű egyesítési mezőt a dokumentumba.

## 3. lépés: Változtassa meg a nyelvet
dátum- és számformázás területi beállításának módosításához módosíthatja a szál jelenlegi kultúráját. Ebben a példában a területi beállítást németre ("de-DE") állítjuk be:

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

A fenti kódban tároljuk az aktuális kultúrát, majd az aktuális szál kultúráját németre állítjuk.

## 4. lépés: Hajtsa végre a körlevélkészítést
Hajtson végre egy körlevél műveletet, és adja meg a dátum értékét a "Dátum" mezőben:

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

Ebben a kódrészletben végrehajtjuk a körlevél-műveletet, és a „Dátum” mező értékeként az aktuális dátumot adjuk meg.

## 5. lépés: Állítsa vissza az eredeti területi beállítást
Miután a körlevél befejeződött, állítsa vissza a szál eredeti kultúráját:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

A fenti kódban visszaállítjuk a szál eredeti kultúráját.

## 6. lépés: Mentse el a dokumentumot
Mentse el a módosított dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Példa forráskódra a nyelvi beállítás megváltoztatásához az Aspose.Words for .NET használatával
Íme a teljes forráskód a Word dokumentumokban az Aspose.Words for .NET használatával történő megváltoztatásához:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan módosíthatja a területi beállításokat a Word dokumentumokban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód felhasználásával mostantól szabályozhatja a dátumok és számok formázását a körlevél-műveletek során. Szabja testre a területi beállításokat igényei szerint, hogy biztosítsa a dokumentumok pontos és következetes formázását.

### GYIK

#### K: Az Aspose.Words kompatibilis a Microsoft Word különböző verzióival?

V: Igen, az Aspose.Words kompatibilis a Microsoft Word különböző verzióival, beleértve a Word 2003-at, a Word 2007-et, a Word 2010-et, a Word 2013-at, a Word 2016-ot és a Word 2019-et.

#### K: Az Aspose.Words támogatja az összetett mezőstruktúrákat?

V: Abszolút! Az Aspose.Words kiterjedt támogatást nyújt összetett mezőstruktúrákhoz, beleértve a beágyazott mezőket, számításokat és feltételes kifejezéseket. Ezzel a hatékony API-val bármilyen típusú mezőszerkezettel dolgozhat.

#### K: Az Aspose.Words támogatja a helyszíni frissítési műveleteket?

V: Igen, az Aspose.Words lehetővé teszi a mezők ütemezett frissítését. Az API segítségével egyszerűen frissítheti a mezőértékeket, frissítheti a számításokat, és végrehajthat más, mezővel kapcsolatos műveleteket.

#### K: Lehetséges a mezőket egyszerű szöveggé konvertálni az Aspose.Words használatával?

A: Természetesen! Az Aspose.Words módszereket biztosít a mezők egyszerű szöveggé alakítására. Ez akkor lehet hasznos, ha formázás vagy mezőhöz kapcsolódó funkciók nélkül kell kibontani a tartalmat.

#### K: Lehetséges-e dinamikus mezőket tartalmazó Word-dokumentumok generálása az Aspose.Words használatával?

V: Abszolút! Az Aspose.Words robusztus funkcionalitást kínál dinamikus mezőket tartalmazó Word-dokumentumok létrehozásához. Előre definiált mezőket tartalmazó sablonokat hozhat létre, és dinamikusan töltheti fel adatokkal, így rugalmas és hatékony megoldást kínál a dokumentumkészítéshez.