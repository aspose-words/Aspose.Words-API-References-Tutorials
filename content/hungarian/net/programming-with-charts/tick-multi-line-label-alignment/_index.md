---
title: Jelölje be a Többsoros címkeigazítást egy diagramon
linktitle: Jelölje be a Többsoros címkeigazítást egy diagramon
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan igazíthat többsoros címkéket egy diagramtengelyen az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-charts/tick-multi-line-label-alignment/
---

Ez az oktatóanyag elmagyarázza, hogyan kell az Aspose.Words for .NET használatával beállítani a többsoros címkék igazítását a diagram tengelyében. A mellékelt forráskód bemutatja, hogyan hozhat létre diagramot, hogyan lehet hozzáférni a tengelyhez, és hogyan módosíthatja a pipacímke igazítását.

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
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## 3. lépés: Állítsa be a pipa címke igazítását

 A többsoros címkék igazításának beállításához nyissa meg a`AxisX` a diagram tulajdonságát, és állítsa be a`TickLabelAlignment` tulajdonság a kívánt igazításhoz. Ebben a példában az igazítást a következőre állítjuk be`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## 4. lépés: Mentse el a dokumentumot

 Végül mentse a dokumentumot a megadott könyvtárba a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Ezzel befejeződik a többsoros címkeigazítás beállításának végrehajtása az Aspose.Words for .NET használatával.

### Példa forráskódra a Tick Multi Line Label Alignmenthez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Ez a tulajdonság csak többsoros címkékre érvényes.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan állíthatja be a többsoros címkék igazítását egy diagramtengelyen az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód felhasználásával új dokumentumot hozhat létre, szórványdiagramot szúrhat be, hozzáférhet a diagram tengelyéhez, és módosíthatja a pipa címke igazítását.

Az Aspose.Words for .NET hatékony funkciókat kínál a Word dokumentumok diagramjainak kezeléséhez. A többsoros címkék pipálása akkor hasznos, ha a tengelycímkék hosszú szöveget tartalmaznak, amelyet tördelni vagy több sorra fel kell osztani. A pipa címke igazításának beállításával szabályozhatja a többsoros címkék vízszintes igazítását a diagram tengelyén belül, így biztosítva az optimális megjelenítést és olvashatóságot.

többsoros címkeigazítás testreszabása lehetővé teszi a diagram megjelenésének finomhangolását, különösen hosszú vagy összetett címkék esetén. A címkék jobbra, balra, középre vagy sorkizárt igazításával a pipacímkék kiegyensúlyozott és tetszetős elrendezését érheti el a tengely mentén.

Az Aspose.Words for .NET segítségével könnyen elérheti és módosíthatja a diagramtengely jelölőcímkék igazítási tulajdonságát, így teljes ellenőrzést biztosít a Word-dokumentumdiagramokon lévő jelölőcímkék megjelenése és elrendezése felett.

### GYIK

#### Q1. Mik azok a többsoros címkék egy diagram tengelyében?
többsoros címkék egy diagram tengelyén azokra a tengelycímkékre utalnak, amelyek több sort ívelnek át, ha a címkeszöveg hosszú, vagy tördelni kell, hogy elférjen a rendelkezésre álló helyen. A címke szövegének csonkolása vagy vizuális zűrzavar helyett a diagram tengelye automatikusan több sorra osztja a címkéket az olvashatóság biztosítása érdekében. A többsoros címkék kipipálása különösen hasznos hosszú kategória- vagy értékcímkék esetén a diagramokban.

#### Q2. Testreszabhatom a pipacímkék igazítását a diagram tengelyében?
 Igen, az Aspose.Words for .NET használatával testreszabhatja a jelölőcímkék igazítását a diagram tengelyében. A hozzáféréssel a`TickLabelAlignment` tulajdona a`ChartAxis` objektumhoz, beállíthatja a kívánt igazítást a pipacímkék számára. Az igazítási lehetőségek közé tartozik a balra, jobbra, középre vagy sorkizárt igazítás. Az igazítás beállításával szabályozható a pipacímkék vízszintes elhelyezése a diagram tengelye mentén, biztosítva a megfelelő olvashatóságot és vizuális megjelenítést.

#### Q3. Mikor érdemes megfontolni a pipa címke igazításának megváltoztatását a diagram tengelyében?
A jelölőcímke igazításának megváltoztatása a diagram tengelyében akkor előnyös, ha hosszú vagy többsoros címkéi vannak, amelyek optimális megjelenítést és olvashatóságot igényelnek. Az igazítás beállításával biztosíthatja, hogy a címkék megfelelően igazodjanak és elhelyezkedjenek, elkerülve az átfedést vagy a csonkolást. Fontolja meg a pipa címke igazításának megváltoztatását, ha olyan diagramokkal foglalkozik, amelyek hosszú kategórianevekkel, bőbeszédű értékcímkékkel rendelkeznek, vagy bármilyen más forgatókönyv esetén, amikor az alapértelmezett igazítás nem biztosítja a kívánt vizuális megjelenést.

#### Q4. A pipa-címke igazítása hatással van az egysoros címkékre a diagram tengelyében?
Nem, a pipa címke igazítási tulajdonsága nincs hatással a diagramtengely egysoros címkéire. Kifejezetten többsoros címkékhez készült, amelyek csomagolást vagy felosztást igényelnek. Az egysoros címkék igazítása a diagram tengelyének alapértelmezett igazítási beállításai alapján történik. A jelölőcímke igazítási tulajdonsága csak azokra a címkékre vonatkozik, amelyek több vonalon átnyúlnak, lehetővé téve az egyes sorok igazításának szabályozását a többsoros címkén belül.

#### Q5. Rendelhetem-e másképp a pipacímkéket az X és Y tengelyen a diagramon?
 Igen, az Aspose.Words for .NET segítségével eltérő módon igazíthatja a pipacímkéket az X- és Y-tengelyhez egy diagramon. A jelölőcímke igazítási tulajdonsága minden diagramtengelyre jellemző. A megfelelő elérésével`ChartAxis` objektumhoz az X- vagy Y-tengelyhez, egymástól függetlenül beállíthatja a pipacímke igazítását különböző értékekre. Ez rugalmasságot biztosít a pipacímkék eltérő igazítására a diagram egyes tengelyeire vonatkozó speciális követelmények alapján.