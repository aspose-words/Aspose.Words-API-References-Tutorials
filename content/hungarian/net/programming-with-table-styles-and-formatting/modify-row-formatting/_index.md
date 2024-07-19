---
title: Sorformázás módosítása
linktitle: Sorformázás módosítása
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a táblázat sorformázásának megváltoztatásához az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a táblázatsorok formázásának az Aspose.Words for .NET segítségével történő módosításához. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén tudni fogja, hogyan módosíthatja a Word-dokumentumokban lévő táblázatsorok szegélyeit, magasságát és sortörését az Aspose.Words for .NET segítségével.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Itt található a Word-dokumentum. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a meglévő dokumentumot
 Ezután be kell töltenie a meglévő Word-dokumentumot a`Document` osztály.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3. lépés: Nyissa meg a sort a módosításhoz
 Egy táblázatsor formázásának megváltoztatásához a táblázatban az adott sorhoz kell navigálnunk. Használjuk a`GetChild()`és`FirstRow` módszerek a táblázat első sorára való hivatkozás lekéréséhez.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## 4. lépés: Módosítsa a sor formázását
 Most megváltoztathatjuk a sor formázását a tulajdonságok segítségével`RowFormat` osztály. Például eltávolíthatjuk a vonalszegélyeket, beállíthatjuk az automatikus magasságot és engedélyezhetjük a sortörést.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Minta forráskód a sorformázás módosításához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Keresse ki a táblázat első sorát.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan módosítható egy táblázatsor formázása az Aspose.Words for .NET használatával. Ennek a lépésenkénti útmutatónak a követésével könnyedén beállíthatja a Word-dokumentumokban lévő táblázatok szegélyeit, magasságát és sortörését. Az Aspose.Words hatékony és rugalmas API-t kínál a dokumentumok táblázatainak kezeléséhez és formázásához. Ezzel a tudással testreszabhatja asztalai vizuális elrendezését az Ön egyedi igényei szerint.