---
title: Táblázat összeállítása Word dokumentumban
linktitle: Táblázat összeállítása Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan készíthet táblázatot Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/add-content-using-documentbuilder/build-table/
---
Ebből a lépésenkénti oktatóanyagból megtudhatja, hogyan készíthet táblázatot Word-dokumentumban az Aspose.Words for .NET használatával. Végigvezetjük a folyamaton, és biztosítjuk a szükséges C# kódrészleteket. Az útmutató végére a DocumentBuilder osztály segítségével létrehozhat egy táblázatot egyéni formázással és tartalommal.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy új dokumentumot
Kezdésként hozzon létre egy új dokumentumot a Dokumentum osztály használatával:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Indítsa el a táblázatot
Ezután használja a DocumentBuilder osztály StartTable metódusát a tábla felépítéséhez:

```csharp
Table table = builder.StartTable();
```

## 3. lépés: Cellák beszúrása és tartalom hozzáadása
Most már beszúrhat cellákat a táblázatba, és tartalmat adhat hozzájuk a DocumentBuilder osztály InsertCell és Write metódusaival. Igény szerint testreszabhatja a cella formázását:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## 4. lépés: Zárja be a sort
Miután hozzáadott tartalmat az első sor celláihoz, használja a DocumentBuilder osztály EndRow metódusát a sor befejezéséhez:

```csharp
builder.EndRow();
```

## 5. lépés: A sorformázás testreszabása
Testreszabhatja egy sor formázását a RowFormat és CellFormat objektumok tulajdonságainak beállításával:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## 6. lépés: Zárja be a táblázatot
A táblázat kitöltéséhez használja a DocumentBuilder osztály EndTable metódusát:

```csharp
builder.EndTable();
```

### Példa forráskódra táblázat készítéséhez Aspose.Words for .NET használatával
Íme a teljes forráskód egy tábla Aspose.Words for .NET használatával történő felépítéséhez:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan készíthet táblázatot Word-dokumentumban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a megadott forráskód felhasználásával most már létrehozhat táblázatokat egyéni formázással.

### GYIK a Word-dokumentum összeállítási táblázatához

#### K: Mi az Aspose.Words for .NET?

V: Az Aspose.Words for .NET egy hatékony dokumentumfeldolgozó könyvtár, amely lehetővé teszi a fejlesztők számára Microsoft Word dokumentumok létrehozását, olvasását, szerkesztését és programozott konvertálását .NET-alkalmazásokban. Funkciók széles skáláját kínálja a Word-dokumentumokkal való munkavégzéshez, mint például szövegkezelés, táblázatkészítés, dokumentumvédelem, formázás stb.

#### K: Hogyan építhetek táblázatot Word-dokumentumban az Aspose.Words for .NET használatával?

V: Ha Word-dokumentumban szeretne táblázatot készíteni az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:
1.  Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder` tárgy.
2.  Használja a`StartTable` módszere a`DocumentBuilder`osztályt, hogy elkezdhessék az asztal építését.
3.  Szúrjon be cellákat a táblázatba, és adjon hozzá tartalmat a`InsertCell` és`Write` módszerei a`DocumentBuilder` osztály.
4.  A sort a gombbal fejezze be`EndRow` módszere a`DocumentBuilder` osztály.
5.  Testreszabhatja a sor formázását a tulajdonságok beállításával`RowFormat` és`CellFormat` tárgyakat.
6.  A táblázatot a gombbal fejezze be`EndTable` módszere a`DocumentBuilder` osztály.
7. Mentse el a dokumentumot.

#### K: Hogyan szabhatom testre a táblázat és celláinak formázását?

 V: Testreszabhatja a táblázat és celláinak formázását a különböző tulajdonságok beállításával`RowFormat` és`CellFormat` tárgyakat. Beállíthatja például a cellaigazítást, a függőleges és vízszintes szövegtájolást, a cellamagasságot, a sormagasságot stb. Ezen tulajdonságok használatával elérheti a kívánt megjelenést a táblázatnak és annak tartalmának.

#### K: Építhetek összetett táblázatokat egyesített cellákkal és egyéb speciális szolgáltatásokkal?

 V: Igen, az Aspose.Words for .NET fejlett szolgáltatásokat nyújt összetett táblák készítéséhez, beleértve az egyesített cellák, beágyazott táblák és összetett táblaelrendezések támogatását. Használhatja a`MergeCells` cellák egyesítésének módja,`StartTable`metódussal beágyazott táblák létrehozásához, és egyéb módszereket a kívánt táblastruktúra eléréséhez.

#### K: Az Aspose.Words for .NET kompatibilis a különböző Word dokumentumformátumokkal?

V: Igen, az Aspose.Words for .NET kompatibilis különféle Word-dokumentumformátumokkal, beleértve a DOC-t, DOCX-et, RTF-et és még sok mást. Támogatja a régebbi formátumokat (DOC) és a modern XML-alapú formátumokat (DOCX), és lehetővé teszi, hogy problémamentesen dolgozzon a különböző formátumú dokumentumokkal.

#### K: Hol találhatok további információt és dokumentációt az Aspose.Words for .NET-hez?

 V: Átfogó dokumentációt és kódpéldákat talál a webhelyen[API hivatkozások](https://reference.aspose.com/words/net/). A dokumentáció részletes információkat tartalmaz a könyvtár szolgáltatásairól és azok használatáról a .NET-alkalmazásokban.