---
title: Függőleges összevonás
linktitle: Függőleges összevonás
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet függőleges egyesíteni a cellákat egy táblázatban egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-tables/vertical-merge/
---

Ebben az oktatóanyagban megtanuljuk, hogyan lehet függőleges egyesíteni a cellákat egy Word-dokumentum táblázatában az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végén képes lesz függőleges egyesíteni a cellákat a Word dokumentumok táblázataiban.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum betöltése
A szövegszerkesztés elindításához a dokumentummal, kövesse az alábbi lépéseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozzon létre egy új dokumentumot
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: Cellák függőleges egyesítése
Ezután összevonjuk a táblázat függőleges celláit. Használja a következő kódot:

```csharp
// Helyezzen be egy cellát
builder. InsertCell();

// Alkalmazza a függőleges egyesítést az első cellára
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Szúrjon be egy másik cellát
builder. InsertCell();

// Ne alkalmazzon függőleges egyesítést a cellára
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Helyezzen be egy cellát
builder. InsertCell();

// Alkalmazza a függőleges összevonást az előző cellával
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Szúrjon be egy másik cellát
builder. InsertCell();

// Ne alkalmazzon függőleges egyesítést a cellára
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Fejezze be a táblázat létrehozását
builder. EndTable();
```

Ebben a kódban a DocumentBuilder konstruktort használjuk cellák beszúrására egy táblázatba. A CellFormat.VerticalMerge tulajdonság segítségével függőleges összevonást alkalmazunk a cellákban. Az első cellaegyesítéshez a CellMerge.First-et, a CellMerge.Previous-t az előző cellával való egyesítéséhez, a CellMerge.None-t pedig a függőleges egyesítéshez használjuk.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot az egyesített cellákkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Vertical Merge számára az Aspose.Words for .NET használatával 
```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Ez a cella függőlegesen össze van vonva a fenti cellával, és üresnek kell lennie.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet függőleges egyesíteni a cellákat egy Word-dokumentum táblázatában az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, könnyedén egyesítheti a Vertical cellákat a táblázatokban.