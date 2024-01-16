---
title: Formázott táblázat
linktitle: Formázott táblázat
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre formázott táblázatot Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-tables/formatted-table/
---

Ebben az oktatóanyagban megtanuljuk, hogyan hozhat létre formázott táblázatot Word-dokumentumban az Aspose.Words for .NET használatával. A kód megértéséhez és ennek a funkciónak a megvalósításához lépésről lépésre követjük az útmutatót. Az oktatóanyag végén egyéni formátumú táblázatokat hozhat létre a Word-dokumentumokban programozottan.

## 1. lépés: A projekt beállítása
1. Indítsa el a Visual Studio programot, és hozzon létre egy új C# projektet.
2. Adjon hozzá hivatkozást az Aspose.Words for .NET könyvtárra.

## 2. lépés: A dokumentum létrehozása és a dokumentumgenerátor inicializálása
A formázott táblázat felépítéséhez új dokumentumot kell létrehoznunk, és inicializálnunk kell a dokumentumgenerátort. Kovesd ezeket a lepeseket:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozza létre a dokumentumot, és inicializálja a dokumentumgenerátort
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 3. lépés: A formázott táblázat elkészítése
Ezután elkészítjük a formázott táblázatot a dokumentumkészítő által biztosított módszerekkel. Használja a következő kódot:

```csharp
// Kezdje el a tömb felépítését
Table table = builder. StartTable();

// A táblázat fejlécsorának felépítése
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// A tömbtest felépítése
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// A tömbépítés vége
builder. EndTable();
```

 Itt a dokumentumkészítőt használjuk a táblázat elkészítéséhez lépésről lépésre. Hívással kezdjük`StartTable()` a táblázat inicializálásához. Akkor használjuk`InsertCell()` sejtek beillesztésére és`Write()` hogy tartalmat adjon az egyes cellákhoz. Különböző formázási tulajdonságokat is használunk a táblázatsorok, cellák és szövegek formázásának meghatározására.

## 4. lépés: Mentse el a dokumentumot
Végül el kell mentenünk a formázott táblázatot tartalmazó dokumentumot. Használja a következő kódot:

```csharp
// Mentse el a dokumentumot
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg a kimeneti dokumentumhoz.

### Formázott táblázat mintaforráskódja az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Táblázatszintű formázást kell alkalmazni, miután legalább egy sor szerepel a táblázatban.
	table.LeftIndent = 20.0;
	// Állítsa be a magasságot, és határozza meg a magasságszabályt a fejlécsorhoz.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Nem kell megadnunk ennek a cellának a szélességét, mert az az előző cellából öröklődött.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Állítsa vissza a magasságot, és határozzon meg egy másik magasságszabályt az asztal törzséhez.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// A betűtípus formázásának visszaállítása.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre formázott táblázatot Word-dokumentumban az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, és implementálja a mellékelt C# kódot, akkor programozottan hozhat létre egyedi formátumú táblázatokat a Word-dokumentumokban. Ez a funkció lehetővé teszi az adatok vizuálisan tetszetős és szervezett megjelenítését és strukturálását.