---
title: Egyszerű oszlopdiagram beszúrása Word dokumentumba
linktitle: Egyszerű oszlopdiagram beszúrása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be egy egyszerű oszlopdiagramot egy dokumentumba az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/insert-simple-column-chart/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET egy egyszerű oszlopdiagram dokumentumba történő beillesztéséhez. A mellékelt forráskód bemutatja a diagram létrehozását, a sorozatadatok hozzáadását és a dokumentum mentését.

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

 Ezután használja a`InsertChart` módszere a`DocumentBuilder` oszlopdiagram beszúrásához a dokumentumba. Igényei szerint különböző diagramtípusokat és méreteket adhat meg.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában több sorozatot adunk hozzá két-két kategóriával.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Ezzel befejeződik egy egyszerű oszlopdiagram beszúrása az Aspose.Words for .NET használatával.

### Példa forráskód az egyszerű oszlopdiagram beszúrásához az Aspose.Words használatával .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Különféle diagramtípusokat és méreteket adhat meg.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Alapértelmezett generált sorozat törlése.
	seriesColl.Clear();
	// Hozzon létre kategórianevek tömbjét, ebben az oktatóanyagban két kategóriánk van.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Felhívjuk figyelmét, hogy az adattömbök nem lehetnek üresek, és a tömböknek azonos méretűeknek kell lenniük.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan illeszthet be egy egyszerű oszlopdiagramot egy Word-dokumentumba az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a megadott forráskód használatával új dokumentumot hozhat létre, oszlopdiagramot szúrhat be, több sorozatot adhat hozzá kategóriákkal és megfelelő értékekkel, és mentheti a dokumentumot a diagrammal együtt.

Az Aspose.Words for .NET hatékony és rugalmas API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz. Az egyszerű oszlopdiagram hatékony módja a különböző kategóriákban lévő adatok ábrázolásának és összehasonlításának. Az Aspose.Words for .NET segítségével egyszerűen hozhat létre oszlopdiagramokat egyéni adatokkal, több sorozatot adhat hozzá a vizuális összehasonlításhoz, és az Ön igényei szerint testreszabhatja a diagram megjelenését.

Az Aspose.Words for .NET használatával automatizálhatja a dokumentumok oszlopdiagramokkal történő előállítását, így időt és erőfeszítést takaríthat meg a kézi dokumentumkészítés során. A könyvtár diagramtípusok széles skáláját kínálja, beleértve az egyszerű oszlopdiagramokat, és különféle testreszabási lehetőségeket kínál a diagram megjelenésének az Ön igényeihez igazításához.

### GYIK

#### Q1. Mi az oszlopdiagram?
Az oszlopdiagram egy olyan típusú diagram, amely változó magasságú függőleges sávok segítségével jeleníti meg az adatokat. Minden oszlop egy kategóriát képvisel, és az oszlop magassága megfelel az adott kategória értékének. Az oszlopdiagramokat általában a különböző kategóriák adatainak összehasonlítására vagy az időbeli változások nyomon követésére használják.

#### Q2. Hozzáadhatok több sorozatot az oszlopdiagramhoz?
Igen, az Aspose.Words for .NET használatával több sorozatot is hozzáadhat az oszlopdiagramhoz. Minden sorozat adatpontok halmazát képviseli a hozzájuk tartozó kategóriákkal és értékekkel. Több sorozat hozzáadásával összehasonlíthatja és elemezheti a különböző adatkészleteket ugyanazon az oszlopdiagramon belül, így átfogó képet ad az adatokról.

#### Q3. Testreszabhatom az oszlopdiagram megjelenését?
Igen, az Aspose.Words for .NET lehetővé teszi az oszlopdiagram megjelenésének különböző szempontjainak testreszabását. Módosíthatja a tulajdonságokat, például a sorozat színét, a tengelycímkéket, az adatcímkéket és a diagramterület formázását. A könyvtár API-k gazdag készletét kínálja a diagram vizuális elemeinek vezérléséhez és az igényeinek megfelelő testreszabott megjelenés létrehozásához.

#### Q4. Elmenthetem a dokumentumot a beillesztett oszlopdiagrammal különböző formátumokban?
 Igen, az Aspose.Words for .NET lehetővé teszi a dokumentum elmentését a beillesztett oszlopdiagrammal különféle formátumokban, például DOCX, PDF, HTML és egyebekben. Kiválaszthatja a kívánt kimeneti formátumot igényei alapján, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez. A beszúrt oszlopdiagram megmarad a mentett dokumentumban.

#### Q5. Módosíthatom az oszlopdiagram adatait és megjelenését a beillesztés után?
Igen, miután beszúrta az oszlopdiagramot a dokumentumba, az Aspose.Words for .NET által biztosított API-k segítségével módosíthatja annak adatait és megjelenését. Frissítheti a sorozatadatokat új kategóriákkal és értékekkel, módosíthatja az oszlopok színét és formázását, testreszabhatja a tengely tulajdonságait, és különféle formázási beállításokat alkalmazhat dinamikus és tetszetős diagramok létrehozásához a Word-dokumentumokban.