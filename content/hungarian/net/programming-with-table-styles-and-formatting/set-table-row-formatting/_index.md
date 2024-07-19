---
title: Állítsa be a táblázat sor formázását
linktitle: Állítsa be a táblázat sor formázását
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre a táblázat sorformázásának beállításához az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a táblázat sorformázásának beállításához az Aspose.Words for .NET használatával. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén megtudhatja, hogyan állíthatja be a Word-dokumentumokban lévő táblázatsorok magasságát és kitöltését az Aspose.Words for .NET segítségével.

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

## 3. lépés: Indítson el egy új táblát, és adjon hozzá egy cellát
 táblázat létrehozásának megkezdéséhez használjuk a`StartTable()` metódusával, akkor adunk hozzá egy cellát a táblázathoz a`InsertCell()` módszer.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## 4. lépés: Határozza meg a vonal formázását
 Most már beállíthatjuk a sor formázását a`RowFormat` tárgya a`DocumentBuilder` tárgy. A megfelelő tulajdonságok segítségével beállíthatjuk a sor magasságát és a margókat (paddings).

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## 5. lépés: Állítsa be a táblázat margóit
 Ezután beállíthatjuk a táblázat kitöltését a megfelelő tulajdonságok elérésével`Table` tárgy. Ezek a margók a táblázat összes sorára vonatkoznak.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## 6. lépés: Adjon hozzá tartalmat a sorhoz
 Végül tartalmat adhatunk a sorhoz a dokumentumkészítő segítségével`Writeln()` módszer.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## 7. lépés: Fejezze be a táblázatot és mentse el a dokumentumot
Ban ben

 végén befejezzük a táblázat létrehozását a`EndRow()`és`EndTable()` módszerrel, majd a módosított dokumentumot fájlba mentjük.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Minta forráskód a Set Table Row Formatting programhoz az Aspose.Words for .NET használatával 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell beállítani a táblázatsorok formázását az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével könnyedén beállíthatja a táblázat sorainak magasságát és margóit a Word-dokumentumokban. Az Aspose.Words hatékony és rugalmas API-t kínál a dokumentumok táblázatainak kezeléséhez és formázásához. Ezzel a tudással testreszabhatja asztalai vizuális elrendezését az Ön egyedi igényei szerint.