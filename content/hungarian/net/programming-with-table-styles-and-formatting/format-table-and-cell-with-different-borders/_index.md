---
title: Formázza a táblázatot és a cellát különböző szegéllyel
linktitle: Formázza a táblázatot és a cellát különböző szegéllyel
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató táblázat és cella formázásához különböző szegéllyel az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a táblázat és a cella különböző szegélyekkel történő formázásához az Aspose.Words for .NET használatával. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén megtudhatja, hogyan alkalmazhat egyéni szegélyeket a Word-dokumentumok adott tábláira és celláira az Aspose.Words for .NET segítségével.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahová menteni szeretné a szerkesztett Word-dokumentumot. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Hozzon létre egy új dokumentumot és dokumentumkészítőt
 Ezután létre kell hoznia egy új példányt a`Document` osztályt és egy dokumentumkonstruktort az adott dokumentumhoz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Indítson el egy új táblázatot, és adjon hozzá cellákat
 táblázat létrehozásának megkezdéséhez használjuk a`StartTable()` a dokumentumkészítő metódusával, majd cellákat adunk a táblázathoz a`InsertCell()` módszerrel, és a cellák tartalmát a segítségével írjuk`Writeln()` módszer.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Állítson be szegélyeket az egész táblázathoz.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Kitöltés beállítása ehhez a cellához.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Adjon meg egy másik cella kitöltést a második cellához.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Törölje a cellaformázást a korábbi műveletekből.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Hozzon létre vastagabb szegélyeket a sor első cellájához. Más lesz
// a táblázathoz meghatározott határokhoz képest.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## 4. lépés: Mentse el a dokumentumot

  módosították
Végül mentse a módosított dokumentumot fájlba. Kiválaszthat egy megfelelő nevet és helyet a kimeneti dokumentumnak.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Gratulálok ! Az Aspose.Words for .NET segítségével formázott egy táblázatot és egy cellát különböző szegélyekkel.

### Minta forráskód a különböző szegélyű táblázat és cella formázásához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Állítsa be a szegélyeket az egész táblázathoz.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Állítsa be a cella árnyékolását ehhez a cellához.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Adjon meg más cellaárnyékolást a második cellához.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Törölje a cellaformázást a korábbi műveletekből.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Hozzon létre nagyobb kereteket a sor első cellájához. Ez más lesz
	// a táblázathoz beállított szegélyekhez képest.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell formázni egy táblázatot és egy cellát különböző szegélyekkel az Aspose.Words for .NET használatával. Ennek a lépésről-lépésre szóló útmutatónak a követésével könnyedén testreszabhatja a Word-dokumentumok táblázat- és cellaszegélyeit. Az Aspose.Words hatékony és rugalmas API-t kínál a dokumentumok táblázatainak kezeléséhez és formázásához. Ezzel a tudással javíthatja Word-dokumentumai vizuális megjelenítését, és megfelelhet az egyedi igényeknek.