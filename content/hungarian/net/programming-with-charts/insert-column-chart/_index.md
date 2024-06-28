---
title: Oszlopdiagram beszúrása Word dokumentumba
linktitle: Oszlopdiagram beszúrása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be oszlopdiagramot egy dokumentumba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/insert-column-chart/
---

Ez az oktatóanyag elmagyarázza, hogyan lehet az Aspose.Words for .NET használatával oszlopdiagramot beilleszteni egy dokumentumba. A mellékelt forráskód bemutatja a diagram létrehozását, a sorozatadatok hozzáadását és a dokumentum mentését.

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

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában két kategóriát és a hozzájuk tartozó értékeket adunk hozzá.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Ezzel befejeződik az oszlopdiagram beszúrása az Aspose.Words for .NET használatával.

### Példa forráskódra az Oszlopdiagram beszúrásához az Aspose.Words használatával .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan lehet oszlopdiagramot beszúrni egy Word-dokumentumba az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával új dokumentumot hozhat létre, oszlopdiagramot szúrhat be, sorozatadatokat adhat hozzá, és mentheti a dokumentumot a diagrammal együtt.

Az Aspose.Words for .NET hatékony API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz. Az oszlopdiagramokat általában a különböző kategóriák vagy csoportok adatainak megjelenítésére és összehasonlítására használják. Az Aspose.Words for .NET segítségével egyszerűen hozhat létre oszlopdiagramokat, amelyek hatékonyan jelenítik meg adatait, és értékes betekintést nyújtanak.

Az Aspose.Words for .NET használatával automatizálhatja a dokumentumok oszlopdiagramokkal történő előállítását, így időt és erőfeszítést takaríthat meg a kézi dokumentumkészítés során. A könyvtár diagramtípusok és testreszabási lehetőségek széles skáláját kínálja, lehetővé téve, hogy tetszetős és adatgazdag diagramokat készítsen Word-dokumentumaiban.

### GYIK

#### Q1. Mi az oszlopdiagram?
Az oszlopdiagram egy olyan típusú diagram, amely az adatokat függőleges sávokban vagy oszlopokban jeleníti meg. Minden oszlop jellemzően egy kategóriát vagy csoportot jelöl, az oszlop magassága vagy hossza pedig az adott kategóriához tartozó adatok értékét jelzi. Az oszlopdiagramokat általában a különböző kategóriák adatainak összehasonlítására vagy az időbeli változások nyomon követésére használják.

#### Q2. Hozzáadhatok több sorozatot az oszlopdiagramhoz?
Igen, az Aspose.Words for .NET használatával több sorozatot is hozzáadhat az oszlopdiagramhoz. Minden sorozat adatpontok halmazát képviseli a hozzájuk tartozó kategóriákkal és értékekkel. Több sorozat hozzáadásával összehasonlíthatja és elemezheti a különböző adatkészleteket ugyanazon a diagramon belül, így átfogó képet ad az adatokról.

#### Q3. Testreszabhatom az oszlopdiagram megjelenését?
Igen, az Aspose.Words for .NET használatával testreszabhatja az oszlopdiagram megjelenését. Módosíthatja a tulajdonságokat, például a sorozat színét, a tengelycímkéket, az oszlopszélességet és a diagramterület formázását. A könyvtár API-k gazdag készletét kínálja a diagram vizuális elemeinek vezérléséhez és az igényeinek megfelelő testreszabott megjelenés létrehozásához.

#### Q4. Elmenthetem a dokumentumot a beillesztett oszlopdiagrammal különböző formátumokban?
 Igen, az Aspose.Words for .NET lehetővé teszi a dokumentum elmentését a beillesztett oszlopdiagrammal különféle formátumokban, például DOCX, PDF, HTML és egyebekben. Kiválaszthatja a kívánt kimeneti formátumot igényei alapján, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez. A beszúrt oszlopdiagram megmarad a mentett dokumentumban.

#### Q5. Módosíthatom az oszlopdiagram adatait és megjelenését a beillesztés után?
Igen, miután beszúrta az oszlopdiagramot a dokumentumba, az Aspose.Words for .NET által biztosított API-k segítségével módosíthatja annak adatait és megjelenését. Frissítheti a sorozatadatokat, módosíthatja az oszlopszíneket, testreszabhatja a tengely tulajdonságait, és formázási beállításokat alkalmazhat dinamikus és interaktív diagramok létrehozásához a Word-dokumentumokban.