---
title: Vízszintes összevonás
linktitle: Vízszintes összevonás
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet vízszintesen egyesíteni cellákat Word-táblázatban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/horizontal-merge/
---

Ebben az oktatóanyagban megtanuljuk, hogyan lehet vízszintesen egyesíteni cellákat egy Word-dokumentum táblázatában az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végére képes lesz programozottan egyesíteni a cellákat vízszintesen a Word-táblázatokban.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum létrehozása és a dokumentumgenerátor inicializálása
A táblával és cellákkal való szövegfeldolgozás elindításához új dokumentumot kell létrehoznunk, és inicializálnunk kell a dokumentumgenerátort. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozza létre a dokumentumot, és inicializálja a dokumentumgenerátort
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A táblázat felépítése a cellák vízszintes egyesítésével
Ezután elkészítjük a táblázatot, és vízszintes cellaegyesítést alkalmazunk az Aspose.Words for .NET tulajdonságainak használatával. Használja a következő kódot:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Ez a cella egyesül az előzővel, és üresnek kell lennie.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Itt a dokumentumkészítőt használjuk a táblázat felépítéséhez és a cella vízszintes egyesítési tulajdonságainak beállításához. Használjuk a`HorizontalMerge` tulajdona a`CellFormat` objektumot az egyes cellákra alkalmazandó vízszintes egyesítés típusának megadásához. Használata`CellMerge.First` használat közben egyesítjük az első cellát a következővel`CellMerge.Previous` összevonjuk az aktuális cellát az előző cellával.`CellMerge.None` azt jelzi, hogy a cellát nem szabad összevonni.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a vízszintesen összevont cellákkal. Használja a következő kódot:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a vízszintes egyesítéshez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Ez a cella egyesül az előzővel, és üresnek kell lennie.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet vízszintesen egyesíteni cellákat egy Word-dokumentum táblázatában az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan alkalmazhatja a vízszintes cellaegyesítést a Word-táblázatokban. Ez a funkció lehetővé teszi összetettebb táblázatelrendezések létrehozását és az adatok jobb rendszerezését.