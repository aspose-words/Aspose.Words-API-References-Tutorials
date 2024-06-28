---
title: Diagram tengelyének elrejtése egy Word dokumentumban
linktitle: Diagram tengelyének elrejtése egy Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan rejtheti el a diagram tengelyét egy dokumentumban az Aspose.Words for .NET használatával. A tengely elrejtése tisztább és fókuszáltabb diagrammegjelenítéshez.
type: docs
weight: 10
url: /hu/net/programming-with-charts/hide-chart-axis/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET a diagram tengelyének elrejtéséhez a dokumentumban. A mellékelt forráskód bemutatja a diagram létrehozását, a sorozatadatok hozzáadását és a diagram tengelyének elrejtését.

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

 Ezután szúrjon be egy diagramot a dokumentumba a gombbal`InsertChart` módszere a`DocumentBuilder`. Ebben a példában egy oszlopdiagramot szúrunk be.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában öt elemet és a hozzájuk tartozó értékeket adunk hozzá.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4. lépés: A diagram tengelyének elrejtése

 A diagram tengelyének elrejtéséhez nyissa meg a`AxisY` a diagram tulajdonságát, és állítsa be a`Hidden`tulajdonát`true`.

```csharp
chart.AxisY.Hidden = true;
```

Ebben a példában elrejtjük a diagram Y tengelyét.

## 5. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Ezzel befejeződik a diagram tengelyének elrejtése az Aspose.Words for .NET használatával.

### Példa forráskód a diagramtengely elrejtéséhez az Aspose.Words for .NET használatával 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan rejtheti el a diagram tengelyét egy Word-dokumentumban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával diagramot hozhat létre, sorozatadatokat adhat hozzá, és elrejtheti a diagram tengelyét a kívánt vizuális hatás elérése érdekében.

 Az Aspose.Words for .NET átfogó API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz, amely lehetővé teszi a diagram különböző aspektusainak kezelését, beleértve a tengely tulajdonságait. A hozzáféréssel a`AxisY` a diagram tulajdonságát, elrejtheti az Y tengelyt, hogy eltávolítsa a diagram megjelenítéséből.

A diagram tengelyének elrejtése akkor lehet hasznos, ha a diagramadatokra szeretne fókuszálni anélkül, hogy a tengelyvonalak és címkék elterelnék a figyelmet. Tisztább és minimalista megjelenést biztosít a diagramnak.

Az Aspose.Words for .NET használatával könnyen beépítheti a diagramkészítési képességeket .NET-alkalmazásaiba, és professzionális megjelenésű dokumentumokat hozhat létre testreszabott diagramokkal és rejtett diagramtengelyekkel.

### GYIK

#### Q1. Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy hatékony dokumentumfeldolgozó könyvtár, amely lehetővé teszi a fejlesztők számára Word-dokumentumok programozott létrehozását, kezelését és mentését .NET-alkalmazásokban. Funkciók széles skáláját kínálja a dokumentumelemekkel, köztük diagramokkal és diagramtengelyekkel végzett szövegfeldolgozáshoz.

#### Q2. Hogyan telepíthetem az Aspose.Words for .NET fájlt?
Az Aspose.Words for .NET telepítéséhez a Visual Studio NuGet csomagkezelőjével töltse le. Egyszerűen keresse meg az „Apose.Words” kifejezést a NuGet csomagkezelőben, és telepítse a projektbe.

#### Q3. Elrejthetem a diagram X- és Y-tengelyét is?
 Igen, az Aspose.Words for .NET segítségével elrejtheti a diagram X- és Y-tengelyét is. Az X-tengely elrejtéséhez elérheti a`AxisX` a diagram tulajdonságát, és állítsa be a`Hidden`tulajdonát`true` . Hasonlóképpen, az Y tengely elrejtéséhez elérheti a`AxisY` tulajdonság és állítsa be a`Hidden`tulajdonát`true`. Ez lehetővé teszi mindkét tengely eltávolítását a diagram megjelenítéséből.

#### Q4. Elrejtése után újra megmutathatom a tengelyt?
Igen, az Aspose.Words for .NET használatával elrejtése után újra megjelenítheti a diagram tengelyét. Egy rejtett tengely megjelenítéséhez egyszerűen állítsa be a`Hidden` a megfelelő tulajdonsága`AxisX` vagy`AxisY` tiltakozni`false`. Ezzel a tengely ismét láthatóvá válik a diagramon.

#### Q5. Testreszabhatom a diagram tengelyének egyéb tulajdonságait?
 Igen, az Aspose.Words for .NET lehetővé teszi a diagram tengelyének különféle tulajdonságainak testreszabását, például a tengely címét, címkéit, vonalszínét stb. A hozzáféréssel a`AxisX` és`AxisY` A diagram tulajdonságait módosíthatja, pl`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, és sokan mások. Ezzel finoman szabályozhatja a diagram tengelyének megjelenését és viselkedését.

#### Q6. Elmenthetem a diagramot a rejtett tengellyel különböző fájlformátumokban?
 Igen, az Aspose.Words for .NET lehetővé teszi, hogy a diagramot rejtett tengellyel tartalmazó dokumentumot különféle fájlformátumokba mentse, például DOCX, PDF, HTML stb. Kiválaszthatja a kívánt kimeneti formátumot igényei alapján, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez. A rejtett tengely a mentett dokumentumban megmarad.