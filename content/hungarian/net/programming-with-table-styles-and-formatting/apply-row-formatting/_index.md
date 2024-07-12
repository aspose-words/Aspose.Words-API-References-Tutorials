---
title: Sorformázás alkalmazása
linktitle: Sorformázás alkalmazása
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató sorformázás alkalmazásához egy táblázatban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a sorformázás alkalmazásának folyamatán az Aspose.Words for .NET segítségével. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végére világosan megérti, hogyan formázhatja a táblázat sorait a Word-dokumentumokban az Aspose.Words for .NET használatával.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahová menteni szeretné a szerkesztett Word-dokumentumot. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Hozzon létre egy új dokumentumot és dokumentumkészítőt
 Ezután létre kell hoznia egy új példányt a`Document` osztályt és egy dokumentumkonstruktort az adott dokumentumhoz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Indítson el egy új táblát
 A sorformázás alkalmazásához először egy új táblát kell indítanunk a`StartTable()` a dokumentumkonstruktor módszere.

```csharp
Table table = builder. StartTable();
```

## 4. lépés: Szúrjon be cellát, és lépjen a sorformátumra
Most beszúrhatunk egy cellát a táblázatba, és elérhetjük az adott cella sorformátumát a dokumentumkészítő segítségével`InsertCell()`és`RowFormat` mód.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## 5. lépés: Állítsa be a sor magasságát
 A sormagasság beállításához használjuk a`Height`és`HeightRule` a sorformátum tulajdonságait. Ebben a példában 100 pontos sormagasságot állítunk be, és a`Exactly` szabály.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 6. lépés: Határozza meg a táblázat formázását
 Egyes formázási tulajdonságok magán a táblázaton állíthatók be, és az összes táblázatsorra vonatkoznak. Ebben a példában a táblázat margó tulajdonságait a segítségével állítjuk be`LeftPadding`, `RightPadding`, `TopPadding`és`BottomPadding` tulajdonságait.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 7. lépés: Adjon hozzá tartalmat a sorhoz
Most megtehetjük

 A sorhoz tartalmat fogunk hozzáadni a dokumentumkonstruktor módszereivel. Ebben a példában a`Writeln()` módszer szöveg hozzáadásához a sorhoz.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 8. lépés: Fejezd be a sort és a táblázatot
 Miután hozzáadtuk a tartalmat a sorhoz, a sort a következővel zárhatjuk le`EndRow()` módszerrel, majd fejezze be a táblázatot a`EndTable()` módszer.

```csharp
builder. EndRow();
builder. EndTable();
```

## 9. lépés: Mentse el a módosított dokumentumot
Végül a módosított dokumentumot fájlba mentjük. Kiválaszthat egy megfelelő nevet és helyet a kimeneti dokumentumnak.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Gratulálok ! Az Aspose.Words for .NET használatával sorformázást alkalmazott egy táblázatban.

### Minta forráskód az Apply Row Formatting alkalmazáshoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Ezek a formázási tulajdonságok a táblázatban vannak beállítva, és a táblázat összes sorára vonatkoznak.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet sorformázást alkalmazni egy táblázatban az Aspose.Words for .NET használatával. Ennek a lépésről lépésre szóló útmutatónak a követésével könnyedén integrálhatja ezt a funkciót C#-projektjeibe. A táblázatsorok formázásának manipulálása a dokumentumfeldolgozás alapvető eleme, az Aspose.Words pedig hatékony és rugalmas API-t kínál ennek eléréséhez. Ennek a tudásnak a birtokában javíthatja Word-dokumentumai vizuális megjelenítését, és megfelelhet bizonyos követelményeknek.