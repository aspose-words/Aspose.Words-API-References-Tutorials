---
title: Beágyazott táblázat
linktitle: Beágyazott táblázat
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre beágyazott táblázatot Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/nested-table/
---

Ebben az oktatóanyagban megtanuljuk, hogyan hozhat létre beágyazott táblázatot Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Az oktatóanyag végére programozottan beágyazott táblázatokat hozhat létre Word-dokumentumaiban.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum létrehozása és a dokumentumgenerátor inicializálása
A Szövegfeldolgozás elindításához a dokumentummal és a dokumentumgenerátorral, kövesse az alábbi lépéseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentumkészítés
Document doc = new Document();

// Inicializálja a dokumentumgenerátort
DocumentBuilder builder = new DocumentBuilder(doc);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A beágyazott asztal felépítése
Ezután elkészítjük a beágyazott táblát úgy, hogy cellákat szúrunk be a külső táblába, és hozunk létre egy új táblázatot az első cellában. Használja a következő kódot:

```csharp
// Szúrja be a külső táblázat első celláját
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Illessze be a külső táblázat második celláját
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// A külső asztal megszűnése
builder. EndTable();

// Lépjen a külső táblázat első cellájába
builder.MoveTo(cell.FirstParagraph);

// Építsd meg a belső asztalt
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// A belső asztal vége
builder. EndTable();
```

Itt a dokumentumkészítőt használjuk cellák és tartalom beszúrására a külső táblázatba. Ezután mozgassuk a dokumentumkészítő kurzort a külső tábla első cellájába, és cellák és tartalom beszúrásával építsünk be egy új táblát.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a beágyazott táblával. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és névfájlt adja meg a kimeneti dokumentumhoz.

### Minta forráskód a beágyazott táblázathoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Ez a hívás fontos egy beágyazott tábla létrehozásához az első táblán belül.
	// hívás nélkül az alább beszúrt cellák hozzá lesznek fűzve a külső táblázathoz.
	builder.EndTable();
	// Lépjen a külső táblázat első cellájába.
	builder.MoveTo(cell.FirstParagraph);
	// Építsd meg a belső asztalt.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet beágyazott táblázatot létrehozni egy Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C#-kódot, beágyazott táblákat hozhat létre programozottan a Word-dokumentumokban saját igényei szerint.
