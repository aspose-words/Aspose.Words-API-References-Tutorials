---
title: Stílusos asztal építése
linktitle: Stílusos asztal építése
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre egyéni stílusú táblázat elkészítéséhez az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a stílusos táblázat elkészítésének folyamatán az Aspose.Words for .NET használatával. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén megtudhatja, hogyan hozhat létre egyéni stílusú táblázatot a Word-dokumentumokban az Aspose.Words for .NET használatával.

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

## 3. lépés: Indítson el egy új táblázatot, és szúrjon be egy cellát
 Az asztal építésének megkezdéséhez használjuk a`StartTable()` a dokumentumkészítő metódusával, majd a táblázatba beszúrunk egy cellát a`InsertCell()` módszer.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 4. lépés: Határozza meg a táblázat stílusát
 Most beállíthatjuk a táblázat stílusát a`StyleIdentifier` ingatlan. Ebben a példában a "MediumShading1Accent1" stílust használjuk.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## 5. lépés: Alkalmazza a stílusbeállításokat a táblázatra
 A stílus segítségével megadhatjuk, hogy mely jellemzőket formázza a stílus`StyleOptions` tömb tulajdonsága. Ebben a példában a következő beállításokat alkalmazzuk: "FirstColumn", "RowBands" és "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## 6. lépés: Az asztal méretének automatikus beállítása
 A tömb méretének a tartalma alapján történő automatikus beállításához használjuk a`AutoFit()` módszerrel a`AutoFitBehavior.AutoFitToContents` viselkedés.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## 7. lépés: Adjon hozzá tartalmat a cellákhoz
 Most a cellákhoz adhatunk tartalmat a`Writeln()`és`InsertCell()` a dokumentumkészítő módszerei. Ebben a példában hozzáadjuk a „Cikk” és a „Mennyiség (

kg)" és a megfelelő adatok.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## 8. lépés: Mentse el a módosított dokumentumot
Végül a módosított dokumentumot fájlba mentjük. Kiválaszthat egy megfelelő nevet és helyet a kimeneti dokumentumnak.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Gratulálok ! Most egy egyéni stílusú táblázatot készített az Aspose.Words for .NET használatával.

### Minta forráskód a Build Table With Style programhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// A táblázat formázása előtt legalább egy sort be kell szúrnunk.
	builder.InsertCell();
	// Állítsa be a használt táblázatstílust az egyedi stílusazonosító alapján.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Alkalmazza, hogy mely jellemzőket kell a stílus szerint formázni.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan készítsünk stílusos táblázatot az Aspose.Words for .NET használatával. Ennek a lépésről-lépésre szóló útmutatónak a követésével könnyedén testreszabhatja a Word-dokumentumokban lévő táblázatok stílusát. Az Aspose.Words hatékony és rugalmas API-t kínál a dokumentumok táblázatainak kezeléséhez és formázásához. Ezzel a tudással javíthatja Word-dokumentumai vizuális megjelenítését, és megfelelhet az egyedi igényeknek.