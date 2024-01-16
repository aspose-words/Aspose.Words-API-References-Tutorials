---
title: Testreszabhatja az egydiagram-sorozatokat egy diagramon
linktitle: Testreszabhatja az egydiagram-sorozatokat egy diagramon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szabhat testre egyetlen diagramsorozatot egy diagramon az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/single-chart-series/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egyetlen diagramsorozat testreszabásához egy diagramon. A mellékelt forráskód bemutatja, hogyan hozhat létre diagramot, hogyan lehet hozzáférni adott sorozatokhoz, és hogyan módosíthatja azok tulajdonságait.

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

## 3. lépés: A diagramsorozatok elérése és testreszabása

 Egyetlen diagramsorozat módosításához el kell érnie a`ChartSeries` a diagram objektumai.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Ezzel befejeződik az Aspose.Words for .NET használatával egyetlen diagramsorozat testreszabásának megvalósítása.

### Példa a Single Chart Series forráskódjához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Azt is megadhatja, hogy a diagram pontjait összekötő vonal simításra kerüljön-e Catmull-Rom spline segítségével.
	series0.Smooth = true;
	series1.Smooth = true;
	// Megadja, hogy alapértelmezés szerint a szülőelem megfordítsa-e a színeit, ha az érték negatív.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan szabhat testre egyetlen diagramsorozatot egy diagramban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a megadott forráskód felhasználásával új dokumentumot hozhat létre, vonaldiagramot illeszthet be, hozzáférhet adott diagramsorozatokhoz, és módosíthatja azok tulajdonságait a kívánt testreszabás érdekében.

Az Aspose.Words for .NET hatékony funkciókat kínál a Word dokumentumok diagramjainak kezeléséhez. Az egyes diagramsorozatokhoz való hozzáféréssel speciális módosításokat alkalmazhat azok megjelenésének és viselkedésének testreszabásához. Ez lehetővé teszi a sorozat nevének megváltoztatását, a diagramvonal simításának engedélyezését, az adatpontok markereinek testreszabását, a negatív értékek színeinek megfordítását és még sok mást a diagram vizuális megjelenítésének javítása érdekében.

Egyetlen diagramsorozat testreszabása rugalmasságot biztosít bizonyos adatok kiemeléséhez vagy bizonyos trendek kiemeléséhez a diagramon belül. Az Aspose.Words for .NET segítségével könnyen elérheti és módosíthatja a diagramsorozat tulajdonságait, így tetszetős és informatív diagramokat hozhat létre Word-dokumentumaiban.

### GYIK

#### Q1. Testreszabhatok több diagramsorozatot egy diagramon?
 Igen, testreszabhat több diagramsorozatot egy diagramon az Aspose.Words for .NET használatával. A hozzáféréssel a`ChartSeries` diagramon belüli objektumok esetén több sorozatot is kiválaszthat és módosíthat azok indexei vagy meghatározott kritériumai alapján. Használjon hurkot vagy egyedi hozzárendeléseket az egyes diagramsorozatok kívánt tulajdonságainak módosításához. Így ugyanazon a diagramon belül több sorozatra is alkalmazhat különböző testreszabásokat.

#### Q2. Hogyan változtathatom meg egy diagramsorozat nevét?
 Ha az Aspose.Words for .NET használatával módosítani szeretné egy diagramsorozat nevét egy diagramon, akkor el kell érnie a`Name` tulajdona a`ChartSeries` objektumot, és állítsa be a kívánt névre. A sorozat neve általában a diagram jelmagyarázatában vagy adatcímkéiben jelenik meg, leíró címkét biztosítva a sorozathoz. A sorozat nevének módosításával értelmes neveket adhat meg, amelyek tükrözik az egyes sorozatok által képviselt adatokat.

#### Q3. Mi a diagramsorozat simítása?
 diagramsorozat simítása egy vizuális javítási technika, amely lehetővé teszi a diagram pontjait összekötő sima vonal létrehozását. Simító algoritmust alkalmaz, például Catmull-Rom spline-okat, hogy interpoláljon az adatpontok között, és egy vizuálisan tetszetős görbét hozzon létre. Ha engedélyezni szeretné a sorozatsimítást egy diagramon az Aspose.Words for .NET használatával, nyissa meg a`Smooth` tulajdona a`ChartSeries` objektumot, és állítsa be`true`. A simítás hasznos lehet a szabálytalan ingadozású adatok trendjei vagy mintáinak megjelenítéséhez.

#### Q4. Hogyan szabhatom testre a jelölőket egy diagramsorozat adatpontjaihoz?
 Egy diagramsorozat adatpontjainak markereinek testreszabásához az Aspose.Words for .NET használatával hozzá kell férnie a`Marker` tulajdona a`ChartSeries` objektumot, és módosítsa annak tulajdonságait, mint pl`Symbol` és`Size`. A jelölők a diagramon elhelyezett vizuális mutatók, amelyek az egyes adatpontokat ábrázolják. Számos beépített jelölőszimbólum közül választhat, és beállíthatja azok méretét, hogy kiemelje vagy megkülönböztethesse a sorozaton belüli egyes adatpontokat.

#### Q5. Megfordíthatom a negatív értékek színeit egy diagramsorozatban?
 Igen, megfordíthatja a negatív értékek színeit egy diagramsorozatban az Aspose.Words for .NET használatával. Beállításával a`InvertIfNegative` tulajdona a`ChartSeries` tiltakozni`true`, a negatív értékű adatpontok színei megfordulnak, így vizuálisan elkülönülnek a pozitív értékektől. Ez a funkció hasznos lehet egy diagramsorozat pozitív és negatív értékeinek összehasonlításakor, egyértelmű különbségtételt biztosítva a kettő között.