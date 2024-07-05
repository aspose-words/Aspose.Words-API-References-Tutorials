---
title: A diagram adatcímkéjének testreszabása
linktitle: A diagram adatcímkéjének testreszabása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat hozzá és testreszabhat adatcímkéket egy diagramhoz az Aspose.Words for .NET használatával, hogy további információkat nyújtson az adatpontokról.
type: docs
weight: 10
url: /hu/net/programming-with-charts/chart-data-label/
---

Ez az oktatóanyag elmagyarázza, hogyan lehet adatcímkéket hozzáadni és testreszabni egy diagramban az Aspose.Words for .NET használatával. Az adatcímkék további információkat nyújtanak a diagram adatpontjairól.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder`tiltakozik a dokumentummal való munkavégzésre.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Diagram beszúrása és konfigurálása
 Szúrjon be egy diagramot a dokumentumba a gombbal`InsertChart` módszere a`DocumentBuilder` tárgy. Állítsa be a kívánt diagramtípust és méreteket.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## 4. lépés: Az adatcímkék testreszabása
Hozzáférhet a diagramsorozatok adatcímkegyűjteményéhez, és módosíthatja a különböző tulajdonságokat az adatcímkék megjelenésének testreszabásához.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## 5. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithCharts.ChartDataLabel.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Példa a Chart Data Label forráskódjához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Alapértelmezés szerint, amikor adatcímkéket ad hozzá egy kördiagram adatpontjaihoz, a vezetővonalak megjelennek azokhoz az adatcímkékhez, amelyek
	// messze az adatpontok végén kívül helyezkednek el. A vezetővonalak vizuális kapcsolatot hoznak létre az adatcímke és annak között
	// megfelelő adatpont.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Ez az! Sikeresen hozzáadott és testreszabott adatcímkéket egy diagramhoz az Aspose.Words for .NET használatával.

## Következtetés
Ebből az oktatóanyagból megtanulta, hogyan adhat hozzá és testreszabhat adatcímkéket egy diagramhoz az Aspose.Words for .NET használatával. A lépésenkénti útmutatót követve beszúrhat egy diagramot, hozzáférhet az adatcímkék gyűjteményéhez, és módosíthatja a tulajdonságokat az adatcímkék megjelenésének testreszabásához. Az Aspose.Words for .NET hatékony API-t biztosít a Word-dokumentumokkal és diagramokkal végzett szövegfeldolgozáshoz, amely lehetővé teszi, hogy tetszetős és informatív diagramokat készítsen testreszabott adatcímkékkel.

### GYIK

#### Q1. Mik azok az adatcímkék a diagramban?
A diagramon lévő adatcímkék további információkat nyújtanak a diagramon szereplő adatpontokról. A diagram típusától és konfigurációjától függően értékeket, kategóriákat, sorozatneveket, százalékokat vagy egyéb releváns részleteket jeleníthetnek meg.

#### Q2. Testreszabhatom az adatcímkék megjelenését?
Igen, testreszabhatja az adatcímkék megjelenését a diagramon. Az Aspose.Words for .NET lehetőséget biztosít az adatcímkék különféle tulajdonságainak módosítására, például a jelmagyarázat kulcsok, vezetővonalak, kategórianevek, sorozatnevek, értékek és egyebek megjelenítésére. Beállíthat elválasztókat és formázhatja is a címkéket, hogy megfeleljenek az egyedi követelményeknek.

#### Q3. Hozzáadhatok adatcímkéket bármilyen diagramtípushoz?
Igen, adatcímkéket adhat hozzá különféle típusú diagramokhoz, például oszlopdiagramokhoz, kördiagramokhoz, vonaldiagramokhoz és egyebekhez. Az adatcímkék hozzáadásának és testreszabásának folyamata kissé eltérhet a diagram típusától és a használt könyvtártól vagy eszköztől függően.
