---
title: Vízszintes szabályformátum Word dokumentumban
linktitle: Vízszintes szabályformátum Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan formázhat vízszintes szabályokat Word dokumentumokban az Aspose.Words for .NET használatával. Lépésről lépésre útmutató.
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Ebből az átfogó példából megtudhatja, hogyan formázhat vízszintes szabályt egy Word-dokumentumban az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Az útmutató végére testreszabhatja a vízszintes szabály igazítását, szélességét, magasságát, színét és egyéb tulajdonságait.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy DocumentBuilder programot, és szúrjon be egy vízszintes szabályt
Kezdésként hozzon létre egy DocumentBuilder objektumot, és használja az InsertHorizontalRule metódust egy vízszintes szabály beszúrásához:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## 2. lépés: Nyissa meg a vízszintes szabályformátumot
Ezután nyissa meg az Shape objektum HorizontalRuleFormat tulajdonságát a formázási beállítások lekéréséhez:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## 3. lépés: A formázási beállítások testreszabása
Most már testreszabhatja a vízszintes szabály különféle formázási beállításait. Például beállíthatja az igazítást, a szélességet, a magasságot, a színt és az árnyékolást:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## 4. lépés: Mentse el a dokumentumot
A vízszintes szabály formázása után mentse a dokumentumot fájlba a Dokumentum objektum Mentés metódusával:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Példa forráskód vízszintes szabályformátumhoz az Aspose.Words for .NET használatával
Íme a teljes forráskód egy vízszintes szabály Aspose.Words for .NET használatával formázásához:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Ne felejtse el beállítani a kódot saját igényei szerint, és szükség szerint bővítse további funkciókkal.

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan formázhat vízszintes szabályt egy Word-dokumentumban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód használatával testreszabhatja a vízszintes szabályok megjelenését a dokumentum vizuális elrendezésének javítása érdekében.

Kísérletezzen a különböző formázási lehetőségekkel, hogy elérje a kívánt stílust és hatást a vízszintes szabályokhoz.

### GYIK a vízszintes szabályformátumhoz a Word dokumentumban

#### K: Alkalmazhatok különböző színeket a vízszintes szabályra?

V: Abszolút! Az Aspose.Words for .NET segítségével egyszerűen testreszabhatja a vízszintes szabály színét, ha a Color tulajdonságot a kívánt színértékre állítja. Ez lehetővé teszi, hogy a vízszintes szabályt a dokumentum általános kialakításához igazítsa.

#### K: Beállítható a vízszintes szabály szélessége és magassága?

V: Igen, teljes mértékben Ön szabályozhatja a vízszintes szabály szélességét és magasságát. A WidthPercent és Height tulajdonságok módosításával elérheti a vízszintes szabály kívánt méreteit.

#### K: Módosíthatom a vízszintes szabály igazítását a dokumentumon belül?

V: Természetesen! Az Aspose.Words for .NET lehetővé teszi a vízszintes szabály igazításának megadását az Alignment tulajdonság segítségével. Különféle lehetőségek közül választhat, például középen, balra, jobbra és sorkizárt.

#### K: Alkalmazhatok árnyékolást vagy háttérszínt a vízszintes szabályra?

V: Igen, hozzáadhat árnyékolást vagy háttérszínt a vízszintes szabályhoz. Alapértelmezés szerint a NoShade tulajdonság igaz értékre van állítva, de beállíthatja false értékre, és a megfelelő módszerekkel meghatározhatja az árnyékolást.

#### K: Beilleszthetek több vízszintes szabályt egyetlen dokumentumba?

V: Abszolút! Az Aspose.Words for .NET használatával több vízszintes szabályt is beszúrhat egy Word-dokumentumba. Egyszerűen ismételje meg az oktatóanyag lépéseit, ha szükséges, annyi vízszintes szabály hozzáadásához.