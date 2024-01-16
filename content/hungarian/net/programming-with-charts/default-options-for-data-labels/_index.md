---
title: Állítsa be az adatcímkék alapértelmezett beállításait egy diagramon
linktitle: Állítsa be az adatcímkék alapértelmezett beállításait egy diagramon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthat be alapértelmezett beállításokat a diagramok adatcímkéihez az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/default-options-for-data-labels/
---

Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.Words for .NET fájlt a diagram adatcímkéihez tartozó alapértelmezett beállítások megadásához. A mellékelt kód bemutatja, hogyan hozhat létre diagramot, hogyan adhat hozzá adatsorokat és testreszabhatja az adatcímkéket az Aspose.Words használatával.

## 1. lépés: Állítsa be a projektet

Mielőtt elkezdené, győződjön meg arról, hogy a következő követelmények teljesülnek:

- Aspose.Words for .NET könyvtár telepítve. A telepítéshez letöltheti a NuGet csomagkezelővel.
- Egy dokumentumkönyvtár elérési útja, ahová a kimeneti dokumentum mentésre kerül.

## 2. lépés: Hozzon létre egy új dokumentumot, és szúrjon be egy diagramot

 Először is hozzunk létre egy újat`Document` tárgy és a`DocumentBuilder` a dokumentum felépítéséhez.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ezután beszúrunk egy diagramot a dokumentumba a`InsertChart` módszere a`DocumentBuilder`. Ebben a példában egy kördiagramot szúrunk be.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## 3. lépés: Adjon hozzá adatsorokat a diagramhoz

Most adjunk hozzá egy adatsort a diagramhoz. Ebben a példában három kategóriát és a hozzájuk tartozó értékeket adunk hozzá.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## 4. lépés: Az adatcímkék testreszabása

 A diagram adatcímkéinek testreszabásához el kell érnünk a`ChartDataLabelCollection` sorozathoz társított objektum.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Ezt követően módosíthatjuk a különböző tulajdonságait`labels`objektumot az adatcímkék kívánt beállításainak megadásához. Ebben a példában engedélyezzük a százalék és az érték megjelenítését, letiltjuk a vezetővonalakat, és beállítunk egy egyéni elválasztót.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## 5. lépés: Mentse el a dokumentumot

 Végül a dokumentumot a megadott könyvtárba mentjük a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Ezzel az Aspose.Words for .NET használatával befejeződik az adatcímkék alapértelmezett beállításainak megvalósítása egy diagramon.

### Példa forráskód az Aspose.Words for .NET-hez használt adatcímkék alapértelmezett beállításaihoz 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan állíthat be alapértelmezett beállításokat a diagramok adatcímkéihez az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével diagramot hozhat létre, adatsorokat adhat hozzá, és testreszabhatja az adatcímkéket, hogy megfeleljenek az Ön sajátos követelményeinek. Az Aspose.Words for .NET hatékony API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz, amely lehetővé teszi a különböző diagramelemek kezelését, valamint a kívánt megjelenés és funkcionalitás elérését.

 A tulajdonságok beállításával a`ChartDataLabelCollection` diagramsorozathoz társított objektum segítségével vezérelheti az adatcímkék megjelenítését, beleértve az olyan beállításokat, mint a százalékok, értékek, vezetővonalak és egyéni elválasztók megjelenítése. Ez a rugalmasság lehetővé teszi az adatok hatékony bemutatását és a diagramok vizuális megjelenítésének javítását.

### GYIK

#### Q1. Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára Word-dokumentumok programozott létrehozását, kezelését és mentését .NET-alkalmazások segítségével. Funkciók széles skáláját kínálja a dokumentumelemekkel, beleértve a diagramokat is tartalmazó szövegfeldolgozáshoz.

#### Q2. Hogyan telepíthetem az Aspose.Words for .NET fájlt?
Az Aspose.Words for .NET telepítéséhez a NuGet csomagkezelő használatával töltse le a Visual Studio alkalmazásban. Egyszerűen keresse meg az „Aspose.Words” kifejezést a NuGet csomagkezelőben, és telepítse a projektbe.

#### Q3. Testreszabhatom a diagram egyéb szempontjait az Aspose.Words for .NET használatával?
Igen, az Aspose.Words for .NET lehetővé teszi a diagramok különböző szempontjainak testreszabását, például a diagram típusát, a tengelycímkéket, a jelmagyarázatot, a diagramterületet és egyebeket. A kívánt megjelenés és viselkedés elérése érdekében elérheti és módosíthatja a diagramobjektum különböző tulajdonságait.

#### Q4. Elmenthetem a diagramot különböző formátumokban?
 Igen, az Aspose.Words for .NET támogatja a diagramot tartalmazó dokumentum mentését különböző formátumokban, beleértve a DOCX, PDF, HTML és egyebeket. Kiválaszthatja az igényeinek megfelelő formátumot, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez.

#### Q5. Alkalmazhatom ezeket a technikákat más diagramtípusoknál?
Igen, az ebben az oktatóanyagban leírt technikák alkalmazhatók az Aspose.Words for .NET által támogatott más diagramtípusokra is. A kulcs az, hogy hozzáférjen a szövegfeldolgozáshoz használt diagramtípushoz tartozó releváns objektumokhoz és tulajdonságokhoz.