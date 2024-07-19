---
title: Bontsa ki a Formázást a cellákon és a Stílusból
linktitle: Bontsa ki a Formázást a cellákon és a Stílusból
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a formázás cellákra és sorokra kiterjesztéséhez táblázatstílusból az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a formázási folyamaton a cellákra és sorokra való kiterjesztéséhez egy stílusból az Aspose.Words for .NET segítségével. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén megtudhatja, hogyan alkalmazhat táblázatstílusú formázást a Word-dokumentumok adott celláira és soraira az Aspose.Words for .NET segítségével.


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

## 3. lépés: Lépjen az első táblázat első cellájába
 A kezdéshez a dokumentum első táblázatának első cellájába kell navigálnunk. Használjuk a`GetChild()`és`FirstRow.FirstCell` módszerek az első cellára való hivatkozás lekéréséhez.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## 4. lépés: A kezdeti cellaformázás megjelenítése
táblázat stílusainak kibontása előtt megjelenítjük a cella aktuális háttérszínét. Ennek üresnek kell lennie, mert az aktuális formázás a táblázat stílusában van tárolva.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## 5. lépés: Bontsa ki a Táblázatstílusokat a Közvetlen formázásra
 Most kiterjesztjük a táblázatstílusokat a közvetlen formázásra a dokumentum használatával`ExpandTableStylesToDirectFormatting()` módszer.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## 6. lépés: A cellaformázás megjelenítése a stílusbővítés után
Most a táblázatstílusok kibontása után jelenítjük meg a cella háttérszínét. A táblázat stílusából kék háttérszínt kell alkalmazni.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Forráskód minta a Formázás kibontásához a cellákon és a sorok stílusából az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Szerezze be a dokumentum első táblázatának első celláját.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Először nyomtassa ki a cellaárnyékolás színét.
	// Ennek üresnek kell lennie, mivel az aktuális árnyékolás a táblázatstílusban tárolódik.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Most nyomtassa ki a cella árnyékolását a táblázatstílusok kibontása után.
	// A táblázat stílusából kék háttérmintázatot kellett volna alkalmazni.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan bővíthetjük ki a formázást cellákra és sorokra táblázatstílusból az Aspose.Words for .NET használatával. Ha követi ezt a lépésenkénti útmutatót, könnyen alkalmazhat táblázatstílusú formázást a Word-dokumentumok adott celláira és soraira. Az Aspose.Words hatékony és rugalmas API-t kínál a dokumentumok táblázatainak kezeléséhez és formázásához. Ezzel a tudással tovább testreszabhatja Word-dokumentumai elrendezését és megjelenítését.