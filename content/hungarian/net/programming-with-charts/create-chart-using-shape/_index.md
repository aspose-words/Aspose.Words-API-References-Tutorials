---
title: Diagram létrehozása és testreszabása a Shape segítségével
linktitle: Diagram létrehozása és testreszabása a Shape segítségével
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre és testreszabhat diagramot egy Word-dokumentum alakzatával az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/create-chart-using-shape/
---

Ez az oktatóanyag elmagyarázza, hogyan hozhat létre diagramot egy Word-dokumentum alakzatával az Aspose.Words for .NET használatával.

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
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 4. lépés: A diagram testreszabása
Testreszabhatja a diagramot különféle tulajdonságok, például a diagram címének és jelmagyarázatának módosításával.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## 5. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithCharts.CreateChartUsingShape.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Példa forráskódra a diagram létrehozásához alakzat használatával az Aspose.Words segítségével .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Kérjük, vegye figyelembe, ha null vagy üres érték van megadva címszövegként, akkor automatikusan generált cím jelenik meg.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Ez az! Sikeresen létrehozott egy diagramot egy Word-dokumentum alakzatával az Aspose.Words for .NET használatával.

## Következtetés
Ebből az oktatóanyagból megtanulta, hogyan hozhat létre diagramot egy Word-dokumentum alakzatának használatával az Aspose.Words for .NET használatával. A lépésenkénti útmutatót követve beszúrhat és konfigurálhat egy diagram alakzatot, testreszabhatja a megjelenését, és mentheti a dokumentumot. Az Aspose.Words for .NET szolgáltatásainak átfogó készletét kínálja a Word-dokumentumokkal és diagramokkal végzett szövegfeldolgozáshoz, amely lehetővé teszi, hogy professzionális megjelenésű és tetszetős diagramokat készítsen közvetlenül a .NET-alkalmazásokban.

### GYIK

#### Q1. Létrehozhatok diagramokat Word-dokumentumban az Aspose.Words for .NET használatával?
Igen, az Aspose.Words for .NET segítségével programozottan is létrehozhat diagramokat egy Word-dokumentumban. Az Aspose.Words API-kat és funkciókat biztosít különféle típusú diagramok beillesztéséhez, megjelenésük testreszabásához és a diagramadatok kezeléséhez.

#### Q2. Milyen diagramtípusokat támogat az Aspose.Words for .NET?
Az Aspose.Words for .NET diagramtípusok széles skáláját támogatja, beleértve a vonaldiagramokat, oszlopdiagramokat, kördiagramokat, területdiagramokat, szóródiagramokat stb. Kiválaszthatja a megfelelő diagramtípust az adatok és a megjelenítési követelmények alapján.

#### Q3. Testreszabhatom a létrehozott diagram megjelenését?
Igen, testreszabhatja a létrehozott diagram megjelenését az Aspose.Words for .NET segítségével. Módosíthatja a tulajdonságokat, például a diagram címét, a jelmagyarázat pozícióját, az adatcímkéket, a tengelycímkéket, a színeket és más vizuális elemeket, hogy megfeleljenek az egyedi tervezési és formázási igényeinek.
