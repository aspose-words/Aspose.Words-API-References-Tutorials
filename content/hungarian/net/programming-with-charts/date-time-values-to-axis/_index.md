---
title: Adja hozzá a dátum és idő értékeket a diagram tengelyéhez
linktitle: Adja hozzá a dátum és idő értékeket a diagram tengelyéhez
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat dátum és idő értékeket a diagram tengelyéhez az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/date-time-values-to-axis/
---

Ez az oktatóanyag elmagyarázza, hogyan adhat hozzá dátum és idő értékeket a diagram tengelyéhez az Aspose.Words for .NET használatával.

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
 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder` tiltakozik a dokumentummal való munkavégzésre.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Diagram alakzat beszúrása és konfigurálása
 Szúrjon be egy diagram alakzatot a dokumentumba a`InsertChart` módszere a`DocumentBuilder` tárgy. Állítsa be a kívánt diagramtípust és méreteket.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## 4. lépés: Adjon hozzá adatokat a diagramhoz
Adjon hozzá adatokat a diagramsorozathoz, beleértve a dátum és idő értékeket.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## 5. lépés: Konfigurálja a tengelyt
Állítsa be a diagram X-tengelyét a dátum és idő értékek megjelenítéséhez.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## 6. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithCharts.DateTimeValuesToAxis.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Példa forráskódra a Date Time Values'To Axishez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// A fő mértékegységeket egy hétre, a kisebb mértékegységeket pedig egy napra állítsa.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Ez a példakód létrehoz egy új Word-dokumentumot, beszúr egy oszlopdiagramot dátum és idő értékekkel az X-tengelyre, és elmenti a dokumentumot a megadott könyvtárba.

## Következtetés
Ebben az oktatóanyagban megtanulta, hogyan adhat dátum és idő értékeket a diagram tengelyéhez az Aspose.Words for .NET segítségével. A lépésenkénti útmutatót követve létrehozhat egy diagramot, dátum- és időértékeket adhat hozzá a sorozathoz, és konfigurálhatja a tengelyt a dátum és időértékek pontos megjelenítéséhez. Az Aspose.Words for .NET hatékony szolgáltatáskészletet kínál a Word-dokumentumok diagramjaival a Word-feldolgozáshoz, lehetővé téve az adatok hatékony ábrázolását és megjelenítését dátum- és időértékekkel.

### GYIK

#### Q1. Hozzáadhatok dátum és idő értékeket a diagram tengelyéhez az Aspose.Words for .NET használatával?
Igen, az Aspose.Words for .NET segítségével dátum- és időértékeket adhat hozzá és megjeleníthet egy Word-dokumentum diagram tengelyén. Az Aspose.Words API-kat és funkciókat biztosít a különféle diagramtípusokkal való munkavégzéshez és azok megjelenésének testreszabásához, beleértve a dátum és idő értékek kezelését a tengelyen.

#### Q2. Hogyan adhatok hozzá dátum és idő értékeket a diagramsorozathoz?
 Ha dátum- és időértékeket szeretne hozzáadni a diagramsorozathoz, használja a`Add` diagram sorozatának módszere. Adja meg a dátum és idő értékek tömbjét kategória (X-tengely) adatként, a megfelelő sorozatértékekkel együtt. Ez lehetővé teszi az adatpontok dátum- és időértékekkel való ábrázolását a diagramon.

#### Q3. Hogyan konfigurálhatom a tengelyt a dátum és idő értékek megjelenítésére?
 A megfelelő tulajdonságok beállításával beállíthatja a diagram tengelyét a dátum és idő értékek megjelenítésére. Például megadhatja a tengely minimális és maximális értékét a gombbal`Scaling.Minimum` és`Scaling.Maximum` tulajdonságait, ill. Ezenkívül beállíthatja a fő- és mellékegységeket a tengely intervallumának és pipajeleinek meghatározásához.
