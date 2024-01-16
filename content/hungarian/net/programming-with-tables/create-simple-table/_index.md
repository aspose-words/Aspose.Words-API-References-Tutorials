---
title: Egyszerű táblázat létrehozása
linktitle: Egyszerű táblázat létrehozása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre egyszerű táblázatot Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/create-simple-table/
---

Ebben az oktatóanyagban megtanuljuk, hogyan hozhat létre egyszerű táblázatot Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Az oktatóanyag végén egyéni táblázatokat hozhat létre programozottan a Word-dokumentumokban.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum létrehozása és a dokumentumgenerátor inicializálása
A tábla felépítéséhez új dokumentumot kell létrehoznunk, és inicializálnunk kell a dokumentumkészítőt. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozza létre a dokumentumot, és inicializálja a dokumentumgenerátort
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A tömb felépítése
Ezután elkészítjük a táblázatot a dokumentumkészítő által biztosított módszerekkel. Használja a következő kódot:

```csharp
// Kezdje el a tömb felépítését
builder. StartTable();

// Az első sor első cellájának felépítése
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Az első sor második cellájának felépítése
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Hívja a következő metódust az első sor befejezéséhez és egy új sor indításához
builder. EndRow();

// A második sor első cellájának felépítése
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// A második sor második cellájának építése
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Hívja a következő metódust a második sor befejezéséhez
builder. EndRow();

// Jelzi, hogy az asztal építése befejeződött
builder. EndTable();
```

 Itt a dokumentumkészítőt használjuk a táblázat elkészítéséhez lépésről lépésre. Hívással kezdjük`StartTable()` a táblázat inicializálásához, majd használja`InsertCell()` sejtek beillesztésére és`Write()` tartalom hozzáadásához az egyes cellákhoz. Mi is használjuk`EndRow()` egy sor befejezéséhez és egy új sor indításához. Végül felhívjuk`EndTable()` jelezni, hogy a táblázat elkészítése befejeződött.

## 4. lépés: Mentse el a dokumentumot
Végül meg kell mentenünk

  a dokumentumot a létrehozott táblázattal. Használja a következő kódot:

```csharp
// Mentse el a dokumentumot
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód az egyszerű táblázat létrehozásához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Kezdje el az asztal építését.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Építse meg a második cellát.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Hívja a következő metódust a sor befejezéséhez és egy új sor indításához.
	builder.EndRow();
	// Építse fel a második sor első celláját.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Építse meg a második cellát.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Jelezze, hogy befejeztük az asztal felépítését.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan hozhatunk létre egyszerű táblázatot Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan hozhat létre egyéni táblázatokat a Word-dokumentumokban. Ez a funkció lehetővé teszi az adatok strukturált és áttekinthető formázását és rendszerezését.