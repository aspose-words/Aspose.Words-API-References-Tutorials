---
title: Intervallum Egység Címkék Között Egy Diagram Tengelyén
linktitle: Intervallum Egység Címkék Között Egy Diagram Tengelyén
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be az intervallum mértékegységét a diagram tengelyén lévő címkék között az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET a diagram tengelyén lévő címkék közötti intervallum mértékegységének beállítására. A mellékelt forráskód bemutatja, hogyan hozhat létre diagramot, hogyan adhat hozzá sorozatadatokat és testreszabhatja a tengelycímkéket.

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
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4. lépés: A tengelycímkék testreszabása

 Az X-tengely címkéi közötti intervallum mértékegységének beállításához nyissa meg a`AxisX` a diagram tulajdonságát, és állítsa be a`TickLabelSpacing` ingatlant a kívánt értékre. Ebben a példában a térközt 2-re állítjuk.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## 5. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Ezzel befejeződik a tengelyen lévő címkék közötti intervallum egység beállításának megvalósítása az Aspose.Words for .NET használatával.

### Példa forráskód az Interval Unit Between Labels On Axis programhoz az Aspose.Words for .NET használatával 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan állíthatja be a diagram tengelyén lévő címkék közötti intervallum mértékegységét az Aspose.Words for .NET segítségével. A lépésenkénti útmutató követésével és a megadott forráskód felhasználásával új dokumentumot hozhat létre, oszlopdiagramot szúrhat be, sorozatadatokat adhat hozzá, és testreszabhatja a tengelycímkéket a címkék közötti távolság szabályozásához.

Az Aspose.Words for .NET hatékony funkciókat kínál a Word dokumentumok diagramjainak kezeléséhez. A tengelyen lévő címkék közötti intervallum mértékegységének beállításával szabályozhatja a címkék megjelenítési sűrűségét, és javíthatja a diagramok olvashatóságát. Ez lehetővé teszi az adatok megjelenítésének optimalizálását és az általános felhasználói élmény javítását.

Az Aspose.Words for .NET segítségével rugalmasan testreszabhatja a diagram különböző aspektusait, beleértve a tengelycímkéket. Beállíthatja a kívánt intervallum mértékegységét, hogy biztosítsa a címkék megfelelő távolságát, és az adatpontok egyértelmű ábrázolását.

### GYIK

#### Q1. Mik azok a tengelycímkék a diagramban?
diagram tengelycímkéi az értékek szöveges megjelenítésére utalnak a diagram vízszintes (X-tengely) vagy függőleges (Y-tengely) tengelye mentén. Ezek a címkék segítenek azonosítani és értelmezni a diagramon ábrázolt adatpontokat. A tengelycímkék kontextust biztosítanak, és lehetővé teszik a felhasználók számára, hogy megértsék a diagram skáláját és értéktartományát.

#### Q2. Hogyan szabhatom testre a tengelycímkék közötti távolságot?
 A diagramon a tengelycímkék közötti távolság testreszabásához az Aspose.Words for .NET használatával elérheti a`AxisX` vagy`AxisY` a diagram tulajdonságait, és módosítsa a`TickLabelSpacing` ingatlan. Beállításával a`TickLabelSpacing` egy adott értékhez szabályozhatja a megfelelő tengelyen lévő címkék közötti intervallum mértékegységét, és az Ön igényei szerint állíthatja be a távolságot.

#### Q3. Beállíthatok eltérő távolságot az X-tengely és az Y-tengely címkéihez?
Igen, az Aspose.Words for .NET használatával különböző távolságot állíthat be az X-tengely és az Y-tengely címkéihez. Nyissa meg a megfelelő tengelyt (`AxisX` az X-tengelyhez ill`AxisY` az Y tengelyhez) a diagramon, és módosítsa a`TickLabelSpacing`tengelyenként külön-külön. Ez lehetővé teszi, hogy az X-tengelyen és az Y-tengelyen különböző intervallumegységeket és távolságokat használjon a címkék számára, így finoman szabályozható a diagram megjelenése.

#### Q4. Mi a jelentősége a tengelyen lévő címkék közötti intervallum egységnek?
A tengelyen lévő címkék közötti intervallum mértékegysége határozza meg a diagramon megjelenített egymást követő címkék közötti távolságot. Az intervallum mértékegységének beállításával szabályozhatja a címkék sűrűségét, és gondoskodhat a megfelelő távolságról, hogy elkerülje a túlzsúfoltságot és az átfedést. Az intervallum mértékegységének beállítása lehetővé teszi az adatok olvashatóbb és látványosabb megjelenítését.

#### Q5. Módosíthatom a tengelycímkék egyéb tulajdonságait?
Igen, az Aspose.Words for .NET tulajdonságok széles skáláját kínálja a tengelycímkék megjelenésének és viselkedésének testreszabásához. Módosíthatja a tulajdonságokat, például a betűtípust, a méretet, a színt, a tájolást, az igazítást és egyebeket, hogy elérje a tengelycímkék kívánt formázását és stílusát. A könyvtár széleskörű ellenőrzést biztosít a diagramelemek felett, lehetővé téve, hogy professzionális megjelenésű diagramokat hozzon létre az Ön egyedi igényei szerint.