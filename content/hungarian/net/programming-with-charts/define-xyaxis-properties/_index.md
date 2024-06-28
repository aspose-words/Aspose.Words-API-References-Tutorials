---
title: Határozza meg az XY tengely tulajdonságait egy diagramon
linktitle: Határozza meg az XY tengely tulajdonságait egy diagramon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan határozhatja meg az XY tengely tulajdonságait egy diagramban az Aspose.Words for .NET használatával. Bemutatjuk az X és Y tengely testreszabási lehetőségeit.
type: docs
weight: 10
url: /hu/net/programming-with-charts/define-xyaxis-properties/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET az X és Y tengely tulajdonságainak meghatározására egy diagramon. A mellékelt forráskód bemutatja, hogyan hozhat létre diagramot, hogyan adhat hozzá sorozatadatokat, és hogyan testreszabhatja a tengely tulajdonságait.

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

 Ezután szúrjon be egy diagramot a dokumentumba a gombbal`InsertChart` módszere a`DocumentBuilder`. Ebben a példában egy területdiagramot szúrunk be.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában öt adatpontot adunk hozzá a megfelelő dátumokkal és értékekkel.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## 4. lépés: Az X és Y tengely tulajdonságainak testreszabása

 Az X és Y tengely tulajdonságainak testreszabásához nyissa meg a`ChartAxis` a diagramhoz társított objektumok.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Módosítsa a tulajdonságait`xAxis` és`yAxis`objektumokat az X és Y tengely kívánt opcióinak beállításához. Ebben a példában bemutatunk néhány általános tulajdonságot, amelyek testreszabhatók.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## 5. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Ezzel befejeződik az XY tengely tulajdonságainak diagramban történő meghatározásának megvalósítása az Aspose.Words for .NET használatával.

### Példa forráskód a Define XYAxis tulajdonságokhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Diagram beszúrása
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Módosítsa az X tengelyt dátum helyett kategóriára, így az összes pont egyenlő időközönként kerül az X tengelyre.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Az Y tengely kijelzési egységeiben mérve (száz).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan határozhatja meg az X és Y tengely tulajdonságait egy diagramon az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével diagramot hozhat létre, sorozatadatokat adhat hozzá, és testreszabhatja a tengely tulajdonságait, hogy megfeleljenek az Ön speciális követelményeinek. Az Aspose.Words for .NET átfogó API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz, amely lehetővé teszi a diagram különböző aspektusainak, köztük a tengelyek kezelését.

 hozzáféréssel a`ChartAxis` A diagramhoz társított objektumokkal módosíthatja a tulajdonságokat, például a kategória típusát, a tengelykereszteket, a pipajeleket, a címkepozíciókat, a méretezést stb. Ez a rugalmasság lehetővé teszi a diagram tengelyeinek megjelenésének és viselkedésének testreszabását az adatok hatékony megjelenítése érdekében.

Az Aspose.Words for .NET használatával zökkenőmentesen integrálhatja a diagramkészítési és testreszabási lehetőségeket .NET-alkalmazásaiba, és automatizálhatja a professzionális megjelenésű dokumentumok létrehozását gazdag vizualizációkkal.

### GYIK

#### Q1. Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy hatékony dokumentumfeldolgozó könyvtár, amely lehetővé teszi a fejlesztők számára Word-dokumentumok programozott létrehozását, kezelését és mentését .NET-alkalmazásokban. Funkciók széles skáláját kínálja a dokumentumelemekkel, beleértve a diagramokat is tartalmazó szövegfeldolgozáshoz.

#### Q2. Hogyan telepíthetem az Aspose.Words for .NET fájlt?
Az Aspose.Words for .NET telepítéséhez a Visual Studio NuGet csomagkezelőjével töltse le. Egyszerűen keresse meg az „Apose.Words” kifejezést a NuGet csomagkezelőben, és telepítse a projektbe.

#### Q3. Testreszabhatom a diagram egyéb szempontjait az Aspose.Words for .NET használatával?
Igen, az Aspose.Words for .NET kiterjedt lehetőségeket kínál a diagramok különböző szempontjainak testreszabásához. A tengely tulajdonságainak megadása mellett módosíthatja a diagram típusát, adatsorait, jelmagyarázatát, címét, diagramterületét, adatcímkéit és a diagram sok más elemét. Az API finoman szabályozza a diagram megjelenését és viselkedését.

#### Q4. Létrehozhatok különböző típusú diagramokat az Aspose.Words for .NET használatával?
 Igen, az Aspose.Words for .NET diagramtípusok széles skáláját támogatja, beleértve a területet, sávot, vonalat, kört, szórványt és egyebeket. Használhatja a`ChartType` felsorolás a kívánt diagramtípus megadásához, amikor diagram alakzatot szúr be egy Word dokumentumba.

#### Q5. Elmenthetem a diagramot különböző formátumokban?
Igen, az Aspose.Words for .NET lehetővé teszi a diagramot tartalmazó dokumentum különböző formátumok, például DOCX, PDF, HTML stb. Kiválaszthatja az igényeinek megfelelő formátumot, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez.

#### Q6. Alkalmazhatom ezeket a technikákat egy dokumentum több diagramjára?
 Igen, ezeket a technikákat egy dokumentum több diagramjára is alkalmazhatja, ha minden diagramnál megismétli a szükséges lépéseket. Létrehozhat külön`Chart` és`ChartAxis` objektumokat minden diagramhoz, és ennek megfelelően testreszabhatja tulajdonságaikat. Az Aspose.Words for .NET teljes mértékben támogatja a szövegfeldolgozást, több diagrammal egyetlen dokumentumban.