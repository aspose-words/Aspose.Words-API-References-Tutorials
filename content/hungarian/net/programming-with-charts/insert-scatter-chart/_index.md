---
title: Szórásdiagram beszúrása a Word dokumentumba
linktitle: Szórásdiagram beszúrása a Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be szóródiagramot egy dokumentumba az Aspose.Words for .NET használatával. Sorozatadatok hozzáadása X és Y koordinátákkal.
type: docs
weight: 10
url: /hu/net/programming-with-charts/insert-scatter-chart/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET szóródási diagram dokumentumba történő beszúrásához. A mellékelt forráskód bemutatja a diagram létrehozását, a sorozatadatok hozzáadását és a dokumentum mentését.

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

 Ezután használja a`InsertChart` módszere a`DocumentBuilder` pontdiagram beszúrásához a dokumentumba.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában két X és Y koordinátakészletet adunk hozzá.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Ezzel befejeződik egy szóródiagram beszúrása az Aspose.Words for .NET használatával.

### Példa forráskódra a Scatter Chart beszúrásához az Aspose.Words segítségével a .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan illeszthet be szóródiagramot egy Word-dokumentumba az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával új dokumentumot hozhat létre, szórványdiagramot szúrhat be, sorozatadatokat adhat hozzá X és Y koordinátákkal, és mentheti a dokumentumot a diagrammal együtt.

Az Aspose.Words for .NET átfogó API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz. A szóródiagramok hasznosak az adatok két numerikus változóval történő megjelenítéséhez és elemzéséhez. Az Aspose.Words for .NET segítségével könnyen létrehozhat szóródiagramokat, amelyek bemutatják az X és Y értékek közötti kapcsolatot, és azonosítják az adatok mintáit vagy trendjeit.

Az Aspose.Words for .NET használatával automatizálhatja a dokumentumok szórványdiagramokkal történő előállítását, így időt és erőfeszítést takaríthat meg a kézi dokumentumkészítés során. A könyvtár diagramtípusok széles skáláját kínálja, beleértve a szóródiagramokat is, és különféle testreszabási lehetőségeket kínál a diagram megjelenésének az Ön igényei szerint történő testreszabásához.

### GYIK

#### Q1. Mi az a szóródiagram?
A szóródiagram egy olyan típusú diagram, amely két numerikus változó közötti kapcsolatot jeleníti meg. Ez egy koordináta-rácson ábrázolt pontok sorozatából áll, ahol az egyik változó az X tengelyen, a másik pedig az Y tengelyen van ábrázolva. A szóródiagramok két adatpontkészlet közötti minták, korrelációk vagy trendek azonosítására szolgálnak.

#### Q2. Hozzáadhatok több sorozatot a szóródiagramhoz?
Igen, az Aspose.Words for .NET használatával több sorozatot is hozzáadhat a szóródiagramhoz. Mindegyik sorozat adatpontok halmazát képviseli a megfelelő X és Y koordinátákkal. Több sorozat hozzáadásával összehasonlíthatja és elemezheti a különböző adatkészleteket ugyanazon a szóródiagramon belül, így átfogó képet ad az adatokról.

#### Q3. Testreszabhatom a szóródiagram megjelenését?
Igen, az Aspose.Words for .NET használatával testreszabhatja a szóródiagram megjelenését. Módosíthatja a tulajdonságokat, például a sorozat színét, a marker alakját, a tengelycímkéket és a diagramterület formázását. A könyvtár API-k gazdag készletét kínálja a diagram vizuális elemeinek vezérléséhez és az igényeinek megfelelő testreszabott megjelenés létrehozásához.

#### Q4. Elmenthetem a dokumentumot a beillesztett pontdiagrammal különböző formátumokban?
Igen, az Aspose.Words for .NET lehetővé teszi a dokumentum elmentését a beillesztett pontdiagrammal különböző formátumokban, például DOCX, PDF, HTML stb. Kiválaszthatja a kívánt kimeneti formátumot igényei alapján, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez. A beszúrt szóródiagram megmarad a mentett dokumentumban.

#### Q5. Módosíthatom a szóródiagram adatait és megjelenését a beillesztés után?
Igen, miután beszúrta a szóródiagramot a dokumentumba, módosíthatja annak adatait és megjelenését az Aspose.Words for .NET által biztosított API-k segítségével. Frissítheti a sorozatadatokat új X és Y koordinátákkal, módosíthatja a jelölők alakját és színét, testreszabhatja a tengely tulajdonságait, és formázási beállításokat alkalmazhat dinamikus és interaktív diagramok létrehozásához a Word-dokumentumokban.