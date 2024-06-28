---
title: Változatok megjelenítése léggömbökben
linktitle: Változatok megjelenítése léggömbökben
second_title: Aspose.Words Document Processing API
description: Változatok megjelenítése buborékokban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-revisions/show-revisions-in-balloons/
---

Ebben a lépésenkénti útmutatóban bemutatjuk, hogyan jelenítheti meg a revíziókat buborékokban egy Word-dokumentumban az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum betöltése

Az első lépés a revíziókat tartalmazó dokumentum feltöltése.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. lépés: Állítsa be az áttekintési megjelenítési beállításokat

A megjelenítési beállításokat úgy konfiguráljuk, hogy a revíziók láthatók legyenek a buborékokban.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## 3. lépés: Mentse el a dokumentumot PDF formátumban

Végül elmentjük a dokumentumot PDF formátumban a buborékokban megjelenő verziókkal.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown kimeneti formátumok

Az olvashatóság javítása érdekében a kimenet markdown-ban formázható. Például :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Példa forráskódra a Revisions In Balloons megjelenítéséhez az Aspose.Words for .NET használatával

Íme a teljes forráskód, amely az Aspose.Words for .NET használatával megjeleníti a revíziókat a buborékokban egy dokumentumban:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// A renderelések beszúrják a revíziókat, a buborékokba pedig törölik és formázzák a revíziókat.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Revíziósávokat jelenít meg az oldal jobb oldalán.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan jeleníthet meg revíziókat buborékokban egy Word-dokumentumban az Aspose.Words for .NET használatával. A megfelelő megjelenítési opciók használatával a revíziókat a jobb oldalon lévő revíziósávokkal buborékokban tudtuk láthatóvá tenni. Az Aspose.Words for .NET számos hatékony szolgáltatást kínál a Word-dokumentumok kezeléséhez, beleértve a revíziókezelést. Mostantól ezt a tudást felhasználhatja saját Word-dokumentumaiban lévő buborékok revízióinak megjelenítésére az Aspose.Words for .NET használatával.


### GYIK

#### K: Hogyan lehet dokumentumot feltölteni az Aspose.Words for .NET-be?

 V: Használja a`Document` osztályú Aspose.Words .NET-hez a dokumentum fájlból való betöltéséhez. Megadhatja a teljes dokumentum elérési utat.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### K: Hogyan jeleníthet meg revíziókat buborékokban az Aspose.Words for .NET segítségével?

 V: Használja a`ShowInBalloons` tulajdona a`RevisionOptions` objektum a revíziók buborékokban való megjelenítésének konfigurálásához. Beállíthatja ezt a tulajdonságot`ShowInBalloons.FormatAndDelete` a revíziók megjelenítése buborékokban a törlési és formázási változatokkal.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### K: Hogyan menthetünk el egy dokumentumot PDF formátumban az Aspose.Words for .NET segítségével?

 V: Használja a`Save` módszere a`Document` objektumot a dokumentum PDF formátumban történő mentéséhez. Meg kell adnia a teljes cél elérési utat a ".pdf" kiterjesztéssel.

```csharp
doc.Save("path/to/destination/document.pdf");
```