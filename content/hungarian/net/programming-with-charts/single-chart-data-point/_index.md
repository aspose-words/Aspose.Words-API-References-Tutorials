---
title: Egyetlen diagram adatpont testreszabása diagramon
linktitle: Egyetlen diagram adatpont testreszabása diagramon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szabhat testre egyetlen adatpontot a diagramon az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/single-chart-data-point/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET a diagram egyetlen adatpontjának testreszabásához. A mellékelt forráskód bemutatja, hogyan hozhat létre diagramot, hogyan férhet hozzá adott adatpontokhoz, és hogyan módosíthatja azok tulajdonságait.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- Aspose.Words for .NET könyvtár telepítve. Letöltheti a NuGet csomagkezelő használatával a telepítéshez.
- Egy dokumentumkönyvtár elérési útja, ahová a kimeneti dokumentum mentésre kerül.

## 2. lépés: Hozzon létre egy új dokumentumot, és szúrjon be egy diagramot

 Újat csinálni`Document` tárgy és a`DocumentBuilder` a dokumentum felépítéséhez.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ezután használja a`InsertChart` módszere a`DocumentBuilder` vonaldiagram beszúrásához a dokumentumba.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Az adatpontok elérése és testreszabása

 Az egyes adatpontok módosításához el kell érnie a`ChartDataPointCollection` sorozatból, és válassza ki a kívánt adatpontot az index segítségével.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Ezzel befejeződik a diagram egyetlen adatpontjának testreszabásának megvalósítása az Aspose.Words for .NET használatával.

### Példa a Single Chart Data Point forráskódjához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan lehet testreszabni egy diagram egyetlen adatpontját az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a megadott forráskód felhasználásával új dokumentumot hozhat létre, vonaldiagramot illeszthet be, hozzáférhet a diagramsorozaton belüli adott adatpontokhoz, és módosíthatja azok tulajdonságait a kívánt testreszabás érdekében.

Az Aspose.Words for .NET hatékony funkciókat kínál a Word dokumentumok diagramjainak kezeléséhez. A diagramsorozaton belüli egyes adatpontokhoz való hozzáféréssel konkrét módosításokat alkalmazhat azok megjelenésének és viselkedésének testreszabásához. Ez lehetővé teszi bizonyos adatpontok kiemelését, a jelölőszimbólumok megváltoztatását, a jelölők méretének beállítását és sok mást, hogy javítsa a diagram vizuális megjelenítését.

Az egyes adatpontok testreszabása rugalmasságot biztosít a fontos adatok kiemeléséhez vagy konkrét trendek kiemeléséhez a diagramon. Az Aspose.Words for .NET segítségével könnyedén elérheti és módosíthatja a különféle diagramtípusok adatpontjait, így tetszetős és informatív diagramokat hozhat létre Word-dokumentumaiban.

### GYIK

#### Q1. Testreszabhatok több adatpontot egy diagramon?
 Igen, testreszabhat több adatpontot egy diagramon az Aspose.Words for .NET használatával. A hozzáféréssel a`ChartDataPointCollection`egy sorozatból több adatpontot is kiválaszthat és módosíthat indexeik alapján. Használjon hurkot vagy egyedi hozzárendeléseket az egyes adatpontok kívánt tulajdonságainak módosításához. Így ugyanazon a diagramon belül több adatpontra is alkalmazhat különböző testreszabásokat.

#### Q2. Hogyan változtathatom meg egy adatpont marker szimbólumát?
 Ha az Aspose.Words for .NET használatával módosítani szeretné egy diagramon lévő adatpont jelölőszimbólumát, el kell érnie a`Marker` tulajdona a`ChartDataPoint` objektumot és állítsa be a`Symbol` tulajdonságot a kívánt marker szimbólumhoz. A jelölőszimbólumok azt az alakzatot vagy ikont képviselik, amely a diagram egyes adatpontjainak megjelenítésére szolgál. Számos beépített jelölőszimbólum közül választhat, például kör, négyzet, rombusz, háromszög, csillag stb.

#### Q3. Beállíthatom az adatpontjelző méretét?
 Igen, az Aspose.Words for .NET segítségével beállíthatja az adatpont-jelölő méretét egy diagramon. Hozzáférés a`Marker` tulajdona a`ChartDataPoint` objektumot és állítsa be a`Size`tulajdonságot a kívánt markerméretre. A marker mérete jellemzően pontokban van megadva, ahol a nagyobb érték nagyobb markerméretet jelent. A marker méretének módosítása lehetővé teszi az adott adatpontok kiemelését vagy azok jelentőségük alapján történő megkülönböztetését.

#### Q4. Milyen egyéb tulajdonságokat módosíthatok egy adatponthoz?
Az Aspose.Words for .NET tulajdonságok széles skáláját kínálja, amelyeket módosíthat egy diagram adatpontjához. A gyakran módosított tulajdonságok közé tartozik a jelölőszimbólum, a jelölő mérete, a jelölő színe, az adatcímke láthatósága, a robbanás, az invert, ha negatív, és így tovább. Ezek a tulajdonságok lehetővé teszik az egyes adatpontok megjelenésének, viselkedésének és interaktivitásának testreszabását, lehetővé téve az egyedi követelményeknek megfelelő diagramok létrehozását.

#### Q5. Testreszabhatom az adatpontokat más diagramtípusokban?
Igen, testreszabhatja az adatpontokat a különböző diagramtípusokban az Aspose.Words for .NET használatával. Míg ez az oktatóanyag egy vonaldiagram adatpontjainak testreszabását mutatja be, hasonló technikákat alkalmazhat más diagramtípusokhoz is, például oszlopdiagramokhoz, oszlopdiagramokhoz, kördiagramokhoz stb. A folyamat magában foglalja a diagramon belüli sorozatok és adatpontok elérését, és azok tulajdonságainak megfelelő módosítását.