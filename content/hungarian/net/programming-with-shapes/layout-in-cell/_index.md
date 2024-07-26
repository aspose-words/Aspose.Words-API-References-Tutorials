---
title: Elrendezés cellában
linktitle: Elrendezés cellában
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan helyezhet el alakzatot egy táblázatcellán belül egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/layout-in-cell/
---

Ez az oktatóanyag elmagyarázza, hogyan helyezhet el alakzatot egy Word-dokumentum táblázatcellájában az Aspose.Words for .NET használatával. Az alakzat tulajdonságainak módosításával és az elrendezési beállítások használatával szabályozhatja az alakzat elhelyezését és megjelenését a cellán belül.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder` tiltakozik a dokumentummal való munkavégzésre.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Építsd meg az asztalt
 Használja a`StartTable`, `EndTable`, `InsertCell` , és`Write` módszerei a`DocumentBuilder` tárgyat építeni egy asztalt. Állítsa be a kívánt sormagasságot és magasságszabályt a gombbal`RowFormat` tulajdonságait.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## 4. lépés: Az alakzat létrehozása és formázása
 Hozzon létre egy`Shape` objektumot, és konfigurálja tulajdonságait a vízjel meghatározásához. Állítsa be a cellán belül elhelyezendő alakzatot a gombbal`IsLayoutInCell` ingatlan.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## 5. lépés: Az alak testreszabása
 Testreszabhatja a vízjel alakzatának megjelenését és szövegét olyan tulajdonságok beállításával, mint pl`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`stb.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## 6. lépés: Illessze be az alakzatot a dokumentumba
 Illessze be a vízjel alakzatot a dokumentumba a gombbal`InsertNode` módszere a`DocumentBuilder` tárgy. Helyezze el az alakzatot a`MoveTo` módszerrel, hogy az utolsó futtatás után helyezze el a dokumentumban.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## 7. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save`módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithShapes.LayoutInCell.docx" néven mentjük.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Példa a Layout In Cell forráskódjához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // Az alakzat megjelenítése a táblázatcellán kívül, ha cellába kerül.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

Ez az! Sikeresen elhelyezett egy alakzatot egy Word-dokumentum táblázatcellájában az Aspose.Words for .NET használatával.