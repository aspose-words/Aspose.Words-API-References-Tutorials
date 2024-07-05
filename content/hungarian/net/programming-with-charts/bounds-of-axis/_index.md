---
title: Tengely határai Egy Chartban
linktitle: Tengely határai Egy Chartban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be egy tengely határait egy diagramon az Aspose.Words for .NET segítségével, amely a tengelyen megjelenített értéktartományt szabályozza.
type: docs
weight: 10
url: /hu/net/programming-with-charts/bounds-of-axis/
---

Ez az oktatóanyag elmagyarázza, hogyan lehet beállítani egy tengely határait egy diagramon az Aspose.Words for .NET használatával. Diagram beszúrásával, sorozatadatok hozzáadásával és a tengely méretezésének konfigurálásával meghatározhatja a tengely minimális és maximális értékét.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 4. lépés: Sorozatadatok hozzáadása
Töröljön minden meglévő sorozatot a diagramból, és adjon hozzá új sorozatadatokat. Ebben a példában „1. tétel” címkékkel ellátott sorozatot adunk az „5. tételhez” és a megfelelő értékekkel.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 5. lépés: Állítsa be a tengely határait
 Konfigurálja az Y tengely méretezését a minimális és maximális értékek beállításával a`Scaling.Minimum` és`Scaling.Maximum` a tengely tulajdonságai.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## 6. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithCharts.BoundsOfAxis.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Példa a Bounds Of Axis forráskódjához az Aspose.Words for .NET használatával 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Ez az! Sikeresen beállította egy diagram tengelyének határait az Aspose.Words for .NET segítségével.

## Következtetés
Ebben az oktatóanyagban megtanulta, hogyan állíthatja be a tengelyek határait egy diagramon az Aspose.Words for .NET használatával. A lépésenkénti útmutatót követve beszúrhat és konfigurálhat diagramot, sorozatadatokat adhat hozzá, és meghatározhatja a tengelyméretezés minimális és maximális értékét. Az Aspose.Words for .NET hatékony és rugalmas API-t biztosít Word-dokumentumokkal végzett szövegfeldolgozáshoz, amely lehetővé teszi dinamikus és tetszetős diagramok egyszerű létrehozását.


### GYIK

#### Q1. Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Word-dokumentumokkal. Szolgáltatások és funkciók széles skáláját kínálja a Word dokumentumok létrehozásához, kezeléséhez és mentéséhez.

#### Q2. Hogyan telepíthetem az Aspose.Words for .NET fájlt?
Az Aspose.Words for .NET telepítéséhez a Visual Studio NuGet csomagkezelőjét használhatja. Egyszerűen keresse meg az „Aspose.Words” kifejezést a NuGet csomagkezelőben, és telepítse a projektbe.

#### Q3. Használhatom az Aspose.Words for .NET-et más programozási nyelvekkel?
Nem, az Aspose.Words for .NET kifejezetten .NET-alkalmazásokhoz készült. Olyan programozási nyelvekkel működik, mint a C# és a VB.NET.

#### Q4. Vannak egyéb előfeltételei az Aspose.Words for .NET használatának?
Az Aspose.Words for .NET könyvtár telepítése mellett alapszintű ismeretekkel kell rendelkeznie a C# programozásról és a Word-dokumentumokkal végzett szövegfeldolgozásról. A .NET keretrendszer ismerete is hasznos lesz.
