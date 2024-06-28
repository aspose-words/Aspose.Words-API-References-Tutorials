---
title: Buborékdiagram beszúrása Word dokumentumba
linktitle: Buborékdiagram beszúrása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be buborékdiagramot egy dokumentumba az Aspose.Words for .NET használatával. Sorozatadatok hozzáadása X, Y és buborékméret értékekkel.
type: docs
weight: 10
url: /hu/net/programming-with-charts/insert-bubble-chart/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET buborékdiagram dokumentumba történő beillesztéséhez. A mellékelt forráskód bemutatja a diagram létrehozását, a sorozatadatok hozzáadását és a dokumentum mentését.

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

 Ezután használja a`InsertChart` módszere a`DocumentBuilder` buborékdiagram beszúrásához a dokumentumba.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában három adatpontot adunk hozzá a megfelelő X, Y és buborékméret értékekkel.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Ezzel befejeződik a buborékdiagram beszúrása az Aspose.Words for .NET használatával.

### Példa forráskódra a Buborékdiagram beszúrásához az Aspose.Words segítségével a .NET-hez 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan illeszthet be buborékdiagramot egy Word-dokumentumba az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával új dokumentumot hozhat létre, buborékdiagramot szúrhat be, sorozatadatokat adhat hozzá, és mentheti a dokumentumot a diagrammal együtt.

Az Aspose.Words for .NET hatékony API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz. A buborékdiagramok ideálisak a háromdimenziós adatok megjelenítésére, ahol minden adatpontot egy buborék képvisel X és Y koordinátákkal és méretértékkel. Az Aspose.Words for .NET segítségével dinamikus és informatív buborékdiagramokat hozhat létre, amelyek javítják az adatok vizuális megjelenítését.

Az Aspose.Words for .NET használatával automatizálhatja a buborékdiagramokkal történő dokumentumok létrehozásának folyamatát, így időt és erőfeszítést takaríthat meg a kézi dokumentumkészítés során. A könyvtár diagramtípusok és testreszabási lehetőségek széles skáláját kínálja, lehetővé téve, hogy tetszetős és adatgazdag diagramokat készítsen Word-dokumentumaiban.

### GYIK

#### Q1. Mi az a buborékdiagram?
buborékdiagram egy olyan típusú diagram, amely háromdimenziós adatokat jelenít meg buborékok vagy gömbök segítségével. Minden adatpontot egy buborék ábrázol, ahol az X és Y koordináták határozzák meg a buborék helyzetét a diagramon, a buborék mérete pedig az adatok harmadik dimenzióját. A buborékdiagramok hasznosak több változó közötti kapcsolatok és minták megjelenítéséhez.

#### Q2. Hozzáadhatok több sorozatot a buborékdiagramhoz?
Igen, az Aspose.Words for .NET használatával több sorozatot is hozzáadhat a buborékdiagramhoz. Minden sorozat adatpontok halmazát képviseli a megfelelő X, Y és buborékméret értékekkel. Több sorozat hozzáadásával összehasonlíthatja és elemezheti a különböző adatkészleteket ugyanazon a diagramon belül, így átfogó képet ad az adatokról.

#### Q3. Testreszabhatom a buborékdiagram megjelenését?
Igen, az Aspose.Words for .NET használatával testreszabhatja a buborékdiagram megjelenését. Módosíthatja a tulajdonságokat, például a sorozat színét, a buborékméretet, a tengelycímkéket és a diagramterület formázását. A könyvtár API-k gazdag készletét kínálja a diagram vizuális elemeinek vezérléséhez és az igényeinek megfelelő testreszabott megjelenés létrehozásához.

#### Q4. Elmenthetem a dokumentumot a beillesztett buborékdiagrammal különböző formátumokban?
 Igen, az Aspose.Words for .NET lehetővé teszi a dokumentum elmentését a beillesztett buborékdiagrammal különböző formátumokban, például DOCX, PDF, HTML stb. Kiválaszthatja a kívánt kimeneti formátumot igényei alapján, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez. A beszúrt buborékdiagram megmarad a mentett dokumentumban.

#### Q5. Módosíthatom a buborékdiagram adatait és megjelenését a beillesztés után?
Igen, miután beszúrta a buborékdiagramot a dokumentumba, az Aspose.Words for .NET által biztosított API-k segítségével módosíthatja annak adatait és megjelenését. Frissítheti a sorozatadatokat, módosíthatja a buborék méretét, testreszabhatja a tengely tulajdonságait, és formázási beállításokat alkalmazhat dinamikus és interaktív diagramok létrehozásához a Word-dokumentumokban.