---
title: Preferált szélesség beállítások
linktitle: Preferált szélesség beállítások
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthat be előnyben részesített táblázatcellaszélességeket egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/preferred-width-settings/
---

Ebből az oktatóanyagból megtudhatja, hogyan állíthatja be a kívánt szélességi beállításokat a Word-dokumentumban lévő táblázatcellákhoz az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Ennek az oktatóanyagnak a végére különböző preferált szélességeket adhat meg a Word-dokumentumokban lévő táblázatcellákhoz.

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

## 3. lépés: Az asztal elkészítése a kívánt szélességgel
Ezután készítünk egy táblázatot három cellával, amelyek eltérő szélességűek. Használja a következő kódot:

```csharp
// A táblázat eleje
builder. StartTable();

// Szúrjon be egy abszolút méretű cellát
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Relatív méretű cella beszúrása (százalékban)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Szúrjon be egy automatikusan méretű cellát
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// A táblázat vége
builder. EndTable();
```

Itt a dokumentumkészítővel három cellát tartalmazó táblázatot készítünk. Az első cella preferált szélessége 40 pont, a második cella preferált szélessége a táblázat szélességének 20%-a, a harmadik cellának pedig automatikus preferált szélessége van, amely beállítja

  a rendelkezésre álló helytől függően.

## 4. lépés: Mentse el a módosított dokumentumot
Végül el kell mentenünk a módosított dokumentumot a táblázatcellákhoz megadott preferált szélességi beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a preferált szélességbeállításokhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Szúrjon be egy táblázatsort, amely három különböző szélességű cellából áll.
	builder.StartTable();
	// Szúrjon be egy abszolút méretű cellát.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Szúrjon be egy relatív (százalékos) méretű cellát.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Szúrjon be egy automatikus méretű cellát.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan adhatunk meg előnyben részesített szélességi beállításokat a Word-dokumentumban lévő táblázatcellákhoz az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, testreszabhatja a táblázat celláinak szélességét a Word-dokumentumok egyedi igényei szerint.