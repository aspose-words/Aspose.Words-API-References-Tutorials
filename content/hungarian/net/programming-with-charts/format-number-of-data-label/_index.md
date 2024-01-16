---
title: Formátum Adatcímke száma A diagramon
linktitle: Formátum Adatcímke száma A diagramon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan formázhatja a diagramon lévő adatcímkék számát az Aspose.Words for .NET segítségével. Egyszerűen testreszabhatja az adatcímkék számformátumait.
type: docs
weight: 10
url: /hu/net/programming-with-charts/format-number-of-data-label/
---

Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.Words for .NET a diagramon lévő adatcímkék számának formázásához. A mellékelt forráskód bemutatja, hogyan hozhat létre diagramot, hogyan adhat hozzá sorozatadatokat, és hogyan szabhatja testre az adatcímkék számformátumát.

## 1. lépés: Állítsa be a projektet

Győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- Aspose.Words for .NET könyvtár telepítve. Letöltheti a NuGet csomagkezelő használatával a telepítéshez.
- Egy dokumentumkönyvtár elérési útja, ahová a kimeneti dokumentum mentésre kerül.

## 2. lépés: Hozzon létre egy új dokumentumot, és szúrjon be egy diagramot

 Újat csinálni`Document` tárgy és a`DocumentBuilder` a dokumentum felépítéséhez.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ezután szúrjon be egy diagramot a dokumentumba a gombbal`InsertChart` módszere a`DocumentBuilder`. Ebben a példában beszúrunk egy vonaldiagramot.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## 3. lépés: Adja hozzá a sorozatadatokat a diagramhoz

Sorozatadatok hozzáadása a diagramhoz. Ebben a példában három kategóriát és a hozzájuk tartozó értékeket adunk hozzá.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## 4. lépés: Az adatcímkék számformátumának testreszabása

 Az adatcímkék számának formázásához nyissa meg a`DataLabels` sorozathoz kapcsolódó gyűjtemény.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Ebben a példában minden adatcímkéhez különböző számformátumokat állítunk be. Az első adatcímke pénznemként, a második dátumként, a harmadik százalékként van formázva.

## 5. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Ezzel befejeződik az adatcímkék számának formázása egy diagramban az Aspose.Words for .NET használatával.

### Példa forráskódra a Format Number Of Data Labelhez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Alapértelmezett generált sorozat törlése.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Vagy beállíthatja, hogy a formátumkód egy forráscellához legyen kapcsolva,
	//ebben az esetben a NumberFormat visszaáll általánosra, és a forráscellából öröklődik.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan kell formázni az adatcímkék számát egy diagramon az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával diagramot hozhat létre, sorozatadatokat adhat hozzá, és igényei szerint testreszabhatja az adatcímkék számformátumát.

 Az Aspose.Words for .NET átfogó API-t biztosít a Word-dokumentumokban lévő diagramokkal a szövegfeldolgozáshoz, lehetővé téve a diagram különböző aspektusainak, köztük az adatcímkék kezelését. A hozzáféréssel a`DataLabels` sorozathoz társított gyűjtemény, testreszabhatja az egyes adatcímkék számformátumát.

Az API lehetővé teszi az értékek megjelenítésének szabályozását, az egyes adatcímkékhez különböző számformátumok beállítását, és a számformátum összekapcsolását egy forráscellával. Ez a rugalmasság lehetővé teszi, hogy diagramokban numerikus adatokat jelenítsen meg a kívánt formázással, például pénznem szimbólumokkal, dátumformátumokkal és százalékértékekkel.

Az Aspose.Words for .NET használatával hatékony diagramkészítési képességeket építhet be .NET-alkalmazásaiba, és professzionális megjelenésű dokumentumokat hozhat létre teljesen formázott diagramokkal és adatcímkékkel.

### GYIK

#### Q1. Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy funkciókban gazdag dokumentumfeldolgozó könyvtár, amely lehetővé teszi a fejlesztők számára Word-dokumentumok programozott létrehozását, kezelését és mentését .NET-alkalmazásokban. Funkciók széles skáláját kínálja a dokumentumelemekkel, köztük diagramokkal és adatcímkékkel ellátott szövegfeldolgozáshoz.

#### Q2. Hogyan telepíthetem az Aspose.Words for .NET fájlt?
Az Aspose.Words for .NET telepítéséhez a Visual Studio NuGet csomagkezelőjével töltse le. Egyszerűen keresse meg az „Aspose.Words” kifejezést a NuGet csomagkezelőben, és telepítse a projektbe.

#### Q3. Formázhatom a diagram egyéb aspektusait az Aspose.Words for .NET használatával?
Igen, az Aspose.Words for .NET kiterjedt lehetőségeket biztosít a diagramok különböző aspektusainak formázásához. Az adatcímkéken kívül testreszabhatja a diagram típusát, a sorozat adatait, a tengely tulajdonságait, a jelmagyarázatot, a címet, a diagram területét és sok más elemet. Az API finoman szabályozza a diagram megjelenését és formázását.

#### Q4. Alkalmazhatok különböző számformátumokat ugyanabban a sorozatban lévő különböző adatcímkékre?
Igen, az Aspose.Words for .NET lehetővé teszi, hogy különböző számformátumokat alkalmazzon ugyanazon a sorozaton belüli egyedi adatcímkékre. A hozzáféréssel a`DataLabels` sorozathoz társított gyűjtemény, beállíthatja a`FormatCode` minden adatcímke tulajdonsága a kívánt számformátum megadásához. Ez lehetővé teszi számértékek megjelenítését különböző formátumokban ugyanazon a diagramon belül.

#### Q5. Használhatok egyéni számformátumokat az adatcímkékhez?
 Igen, az Aspose.Words for .NET támogatja az adatcímkék egyéni számformátumait. A kívánt számformátum beállításával megadhatja a`FormatCode` egy adatcímke tulajdonsága egyéni formátumkódhoz. Ez rugalmasságot biztosít számformátumok széles skálájának alkalmazásához, például pénznemszimbólumok, dátumformátumok, százalékértékek stb.

#### Q6. Elmenthetem a diagramot formázott adatcímkékkel különböző formátumokban?
Igen, az Aspose.Words for .NET lehetővé teszi a diagramot tartalmazó dokumentum mentését formázott adatcímkékkel különféle formátumokban, például DOCX, PDF, HTML stb. Kiválaszthatja az igényeinek megfelelő formátumot, és használhatja a`Save` módszere a`Document` objektumot a dokumentum mentéséhez. A formázott adatcímkék a mentett dokumentumban megmaradnak.