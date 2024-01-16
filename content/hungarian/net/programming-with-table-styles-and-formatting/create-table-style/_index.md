---
title: Táblázatstílus létrehozása
linktitle: Táblázatstílus létrehozása
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre egyéni táblázatstílus létrehozásához az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-table-styles-and-formatting/create-table-style/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a táblázatstílus létrehozásának folyamatán az Aspose.Words for .NET használatával. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén megtudhatja, hogyan hozhat létre egyéni stílust a Word-dokumentumokban lévő táblázatokhoz az Aspose.Words for .NET segítségével.

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

## 3. lépés: Indítson el egy új táblázatot, és adjon hozzá cellákat
 táblázat létrehozásának megkezdéséhez használjuk a`StartTable()` a dokumentumkészítő metódusával, majd cellákat adunk a táblázathoz a`InsertCell()` módszerrel, és a cellák tartalmát a segítségével írjuk`Write()` módszer.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## 4. lépés: Hozzon létre egy táblázatstílust
 Most létrehozhatunk egy táblázatstílust a`TableStyle` osztály és a`Add()` módszer a dokumentumból`s `Styles kollekció. Meghatározzuk a stílus tulajdonságait, például szegélyeket, margókat és kitöltéseket.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## 5. lépés: Alkalmazza a táblázat stílusát az asztalra
 Végül alkalmazzuk a táblázatra az általunk létrehozott táblázatstílust a`Style` az asztal tulajdonsága.

```csharp
table.Style = tableStyle;
```

## 6. lépés: Mentse el a módosított dokumentumot
Végül mentse a módosított dokumentumot fájlba. Kiválaszthat egy megfelelő nevet és helyet a kimeneti dokumentumnak.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Gratulálok ! Most létrehozott egy egyéni stílust a táblázathoz az Aspose.Words for .NET használatával.

### Minta forráskód a Táblázatstílus létrehozásához Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre táblázatstílust az Aspose.Words for .NET használatával. Ennek a lépésről-lépésre szóló útmutatónak a követésével könnyedén testreszabhatja a Word-dokumentumokban lévő táblázatok stílusát. Az Aspose.Words hatékony és rugalmas API-t kínál a dokumentumok táblázatainak kezeléséhez és formázásához. Ezzel a tudással javíthatja Word-dokumentumai vizuális megjelenítését, és megfelelhet az egyedi igényeknek.