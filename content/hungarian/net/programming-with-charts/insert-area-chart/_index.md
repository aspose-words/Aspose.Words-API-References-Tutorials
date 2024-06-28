---
title: Területdiagram beszúrása Word dokumentumba
linktitle: Területdiagram beszúrása Word dokumentumba
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be területdiagramot egy dokumentumba az Aspose.Words for .NET használatával. Adjon hozzá sorozatadatokat, és mentse el a dokumentumot a diagrammal együtt.
type: docs
weight: 10
url: /hu/net/programming-with-charts/insert-area-chart/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET területdiagram dokumentumba történő beillesztéséhez. A mellékelt forráskód bemutatja a diagram létrehozását, a sorozatadatok hozzáadását és a dokumentum mentését.

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

 Ezután használja a`InsertChart` módszere a`DocumentBuilder` területdiagram beszúrásához a dokumentumba.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában öt adatpontot adunk hozzá a megfelelő dátumokkal és értékekkel.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Ezzel befejeződik a területdiagram beszúrása az Aspose.Words for .NET használatával.

### Példa forráskód a Területdiagram beszúrásához az Aspose.Words használatával .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Következtetés

Ebből az oktatóanyagból megtanulta, hogyan lehet területdiagramot beszúrni egy Word-dokumentumba az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával új dokumentumot hozhat létre, területdiagramot szúrhat be, sorozatadatokat adhat hozzá, és mentheti a dokumentumot a diagrammal együtt.

Az Aspose.Words for .NET hatékony API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz. Csak néhány sornyi kóddal professzionális megjelenésű területdiagramokat hozhat létre, és igényei szerint testreszabhatja azokat. A területdiagramokat általában az adatok nagyságrendjének és tendenciáinak időbeli vagy kategóriák szerinti megjelenítésére használják.

Az Aspose.Words for .NET használatával automatizálhatja a dokumentumok területdiagramokkal történő létrehozásának folyamatát, így időt és erőfeszítést takaríthat meg a kézi dokumentumkészítés során. A könyvtár diagramtípusok és testreszabási lehetőségek széles skáláját kínálja, lehetővé téve, hogy tetszetős és informatív diagramokat készítsen Word-dokumentumaiban.

### GYIK

#### Q1. Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy hatékony dokumentumfeldolgozó könyvtár, amely lehetővé teszi a fejlesztők számára Word-dokumentumok programozott létrehozását, módosítását és konvertálását .NET-alkalmazásokban. Átfogó API-készletet biztosít a szövegfeldolgozáshoz dokumentumelemekkel, beleértve diagramokat, bekezdéseket, táblázatokat és sok mást.

#### Q2. Hogyan telepíthetem az Aspose.Words for .NET fájlt?
Az Aspose.Words for .NET telepítéséhez a Visual Studio NuGet csomagkezelőjével közvetlenül a projektbe telepítheti a könyvtárat. Egyszerűen keresse meg az "Apose.Words" kifejezést a NuGet csomagkezelőben, és telepítse a csomagot.

#### Q3. Testreszabhatom a területdiagram megjelenését?
Igen, az Aspose.Words for .NET használatával testreszabhatja a területdiagram megjelenését. Módosíthatja a tulajdonságokat, például a diagram címét, a sorozat színét, a tengelycímkéket és a diagramterület formázását. A könyvtár API-k gazdag készletét kínálja a diagram vizuális elemeinek vezérléséhez és az igényeinek megfelelő testreszabott megjelenés létrehozásához.

#### Q4. Hozzáadhatok több sorozatot a területdiagramhoz?
Igen, több sorozatot is hozzáadhat a területdiagramhoz az Aspose.Words for .NET használatával. Minden sorozat adatpontok halmazát képviseli, amelyek a diagramon vannak ábrázolva. Hozzáadhat sorozatokat különböző adatkészletekkel, és minden sorozatot egyedileg testreszabhat, beleértve a nevét, az adatpontokat és a megjelenést.

#### Q5. Elmenthetem a dokumentumot a beszúrt területdiagrammal különböző formátumokban?
 Igen, az Aspose.Words for .NET lehetővé teszi a dokumentum elmentését a beszúrt területdiagrammal különféle formátumokban, például DOCX, PDF, HTML stb. Kiválaszthatja a kívánt kimeneti formátumot igényei alapján, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez. A beszúrt területdiagram megmarad a mentett dokumentumban.

#### Q6. Módosíthatom a területdiagram adatait és megjelenését a beillesztés után?
Igen, miután beszúrta a területdiagramot a dokumentumba, módosíthatja annak adatait és megjelenését az Aspose.Words for .NET által biztosított API-k segítségével. Frissítheti a sorozat adatait, módosíthatja a diagram típusát, testreszabhatja a tengely tulajdonságait, és formázási beállításokat alkalmazhat dinamikus és interaktív diagramok létrehozásához a Word-dokumentumokban.