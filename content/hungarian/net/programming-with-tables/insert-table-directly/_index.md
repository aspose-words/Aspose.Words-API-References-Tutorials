---
title: Táblázat beszúrása közvetlenül
linktitle: Táblázat beszúrása közvetlenül
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be táblázatot közvetlenül egy Word-dokumentumba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/insert-table-directly/
---

Ebben az oktatóanyagban megtanuljuk, hogyan lehet közvetlenül beszúrni egy táblázatot egy Word-dokumentumba az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Az oktatóanyag végére programozottan közvetlenül beszúrhat táblázatokat Word-dokumentumaiba.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum és a táblázat létrehozása
A Words Processing elindításához a tömbbel egy új dokumentumot kell létrehoznunk, és inicializálnunk kell a tömböt. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentumkészítés
Document doc = new Document();

//Hozd létre a tömböt
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A tömb felépítése
Ezután sorok és cellák hozzáadásával készítjük el a táblázatot. Példaként használja a következő kódot:

```csharp
// Hozza létre az első sort
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Hozza létre az első cellát
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Másolja a cellát a sor második cellájához
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Itt létrehozunk egy sort a`AllowBreakAcrossPages` tulajdonság beállítva`true` hogy lehetővé tegye az oldaltörést a sorok között. Ezután létrehozunk egy cellát színes háttérrel, fix szélességgel és megadott szövegtartalommal. Ezután megkettőzzük ezt a cellát, hogy létrehozzuk a második cellát a sorban.

## 4. lépés: Asztal automatikus illesztése
A táblázat megfelelő formázásához automatikus módosításokat alkalmazhatunk. Használja a következő kódot:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Ez a kódsor a rögzített oszlopszélességeken alapuló automatikus illesztést alkalmaz.

## 5. lépés: Regisztrálja a

  módosított dokumentum
Végül el kell mentenünk a módosított dokumentumot a közvetlenül beszúrt táblázattal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Minta forráskód a Táblázat közvetlen beszúrásához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Kezdjük a táblázat objektum létrehozásával. Ne feledje, hogy át kell adnunk a dokumentum objektumot
	//az egyes csomópontok konstruktorához. Ez azért van, mert minden általunk létrehozott csomópontnak hozzá kell tartoznia
	// valamilyen dokumentumhoz.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Itt hívhatnánk az EnsureMinimum-ot, hogy létrehozza számunkra a sorokat és cellákat. Ezt a módszert alkalmazzák
	// hogy a megadott csomópont érvényes legyen. Ebben az esetben egy érvényes táblázatnak legalább egy sorral és egy cellával kell rendelkeznie.
	// Ehelyett mi magunk készítjük el a sort és a táblázatot.
	// Ez lenne a legjobb módja ennek, ha egy algoritmuson belül hoznánk létre egy táblázatot.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Mostantól bármilyen automatikus illesztési beállítást alkalmazhatunk.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Ezután megismételjük a folyamatot a táblázat többi cellájára és sorára.
	// Meglévő sejtek és sorok klónozásával is felgyorsíthatjuk a dolgokat.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet közvetlenül beszúrni egy táblázatot egy Word-dokumentumba az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan közvetlenül illeszthet be táblázatokat Word-dokumentumaiba. Ez a funkció lehetővé teszi a táblázatok létrehozását és testreszabását az Ön egyedi igényei szerint.