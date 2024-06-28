---
title: Számformátum A tengelyhez egy diagramon
linktitle: Számformátum A tengelyhez egy diagramon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be a diagramon lévő tengelyek számformátumát az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/number-format-for-axis/
---

Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.Words for .NET fájlt egy diagramon lévő tengely számformátumának beállítására. A mellékelt forráskód bemutatja, hogyan hozhat létre diagramot, hogyan adhat hozzá sorozatadatokat és formázhatja a tengelycímkéket.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- Aspose.Words for .NET könyvtár telepítve. Letöltheti a NuGet csomagkezelő használatával a telepítéshez.
- Egy dokumentumkönyvtár elérési útja, ahová a kimeneti dokumentum mentésre kerül.

## 2. lépés: Hozzon létre egy új dokumentumot, és szúrjon be egy diagramot.

 Újat csinálni`Document` tárgy és a`DocumentBuilder` a dokumentum felépítéséhez.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ezután használja a`InsertChart` módszere a`DocumentBuilder` oszlopdiagram beszúrásához a dokumentumba.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában öt elemet adunk hozzá a hozzájuk tartozó értékekkel.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 4. lépés: Formázza meg a tengelycímkéket

 Az Y-tengely címkéinek számformátumának beállításához nyissa meg a`AxisY` a diagram tulajdonságát, és állítsa be a`NumberFormat.FormatCode` tulajdonságot a kívánt formátumba. Ebben a példában a formátumot "#,##0"-ra állítjuk, hogy a számokat ezres elválasztókkal jelenítsük meg.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 5. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Ez befejezi a tengely számformátumának beállítását az Aspose.Words for .NET használatával.

### Példa forráskód az Aspose.Words for Axis számformátumhoz a .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan állíthatja be a diagramon lévő tengelyek számformátumát az Aspose.Words for .NET segítségével. A lépésenkénti útmutató követésével és a megadott forráskód felhasználásával új dokumentumot hozhat létre, oszlopdiagramot szúrhat be, sorozatadatokat adhat hozzá, és formázhatja a tengelycímkéket, hogy a számokat meghatározott formátumban jelenítse meg.

Az Aspose.Words for .NET hatékony funkciókat kínál a diagramok megjelenésének testreszabásához a Word dokumentumokban. A tengelycímkék számformátumának beállításával szabályozhatja a számok megjelenítési módját, beleértve az olyan opciókat is, mint a tizedesjegyek, ezres elválasztók, pénznemszimbólumok stb. Ez lehetővé teszi a numerikus adatok egyértelmű és értelmes megjelenítését.

Az Aspose.Words for .NET segítségével rugalmasan formázhatja a diagram különböző aspektusait, beleértve a tengelycímkéket is. A tengely számformátumának beállításával biztosíthatja a konzisztenciát és javíthatja a diagram olvashatóságát, megkönnyítve a felhasználók számára a megjelenített értékek értelmezését.

### GYIK

#### Q1. Milyen számformátumú a diagram egy tengelye?
A diagramon szereplő tengelyek számformátuma a tengelyen megjelenített számértékekre alkalmazott formázásra vonatkozik. Lehetővé teszi a számok megjelenítésének szabályozását, beleértve az olyan opciókat, mint a tizedesjegyek, ezres elválasztók, valuta szimbólumok, százalékjelek stb. A számformátum beállításával testreszabhatja a numerikus adatok megjelenését a diagramon, hogy megfeleljen az Ön egyedi igényeinek.

#### Q2. Hogyan állíthatom be a tengelycímkék számformátumát?
 A diagramon lévő tengelycímkék számformátumának beállításához az Aspose.Words for .NET használatával elérheti a`AxisY` a diagram tulajdonságát, és állítsa be a`NumberFormat.FormatCode`tulajdonságot a kívánt formátumkódhoz. A formátumkód követi a szabványos numerikus formázási minták szintaxisát, és meghatározza a számok megjelenítési módját. Használhatja például a "#,##0.00" karaktert a számok két tizedesjegyekkel és ezres elválasztókkal való megjelenítéséhez.

#### Q3. Beállíthatok különböző számformátumokat az X-tengely és az Y-tengely címkéihez?
Igen, az Aspose.Words for .NET használatával különböző számformátumokat állíthat be az X-tengely és az Y-tengely címkéihez. Nyissa meg a megfelelő tengelyt (`AxisX` az X-tengelyhez ill`AxisY` az Y-tengelyhez) a diagramon, és módosítsa a`NumberFormat.FormatCode` tengelyenként külön-külön. Ez lehetővé teszi, hogy különböző számformátumokat alkalmazzon az egyes tengelyeken lévő címkékre az Ön egyedi igényei alapján.

#### Q4. Milyen általános számformátumú kódokat használhatok?
Az Aspose.Words for .NET a számformátumkódok széles skáláját támogatja, amelyek segítségével formázhatja a diagram tengelycímkéit. Néhány általános formátumkód:

- `0` vagy`#` - A számot tizedesjegyek nélkül jeleníti meg.
- `0.00` vagy`#.00` - Két tizedesjegy pontossággal jeleníti meg a számot.
- `#,##0` Megjeleníti a számot több ezer elválasztóval.
- `"€"0.00` - Megjeleníti a számot az euró valuta szimbólummal és két tizedesjegygel.
- `"%"0` - A számot százalékban jeleníti meg.

 A számról további információkat találhat[formátumkódok](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) az API Reference of Aspose.Words for .NET-ben.

#### Q5. Testreszabhatom a tengelycímkék egyéb tulajdonságait?
Igen, az Aspose.Words for .NET tulajdonságok széles skáláját kínálja a tengelycímkék megjelenésének és viselkedésének testreszabásához. A számformátumon kívül módosíthatja az olyan tulajdonságokat, mint a betűtípus, méret, szín, tájolás, igazítás stb. Ez lehetővé teszi a tengelycímkék teljes testreszabását, hogy megfeleljenek a kívánt stílusnak és megjelenítési követelményeinek.