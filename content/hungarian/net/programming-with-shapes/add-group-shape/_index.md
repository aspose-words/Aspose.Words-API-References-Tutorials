---
title: Csoportalak hozzáadása
linktitle: Csoportalak hozzáadása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat hozzá több alakzatot tartalmazó csoportalakzatot egy Word-dokumentumhoz az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/add-group-shape/
---

Ez az oktatóanyag elmagyarázza, hogyan adhat hozzá több alakzatot tartalmazó csoportalakzatot egy Word-dokumentumhoz az Aspose.Words for .NET használatával. A csoportos alakzatok lehetővé teszik több alakzat egyetlen entitásként történő kombinálását és kezelését.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"`annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy új dokumentumot és csoportalakzatot
 Hozzon létre egy új példányt a`Document` osztály és`GroupShape` tiltakozik a dokumentummal való munkavégzésre.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## 3. lépés: Hozzon létre és adjon hozzá alakzatokat a GroupShape-hez
 Hozzon létre egyedi formákat, mint pl`accentBorderShape`és`actionButtonShape` használni a`Shape` osztály. Tetszés szerint testreszabhatja tulajdonságaikat. Adja hozzá ezeket az alakzatokat a`groupShape` tárgy.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## 4. lépés: Állítsa be a GroupShape méreteit
Állítsa be a szélességet, magasságot és koordinátaméretet`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## 5. lépés: Illessze be a GroupShape elemet a dokumentumba
 Hozzon létre egy`DocumentBuilder` objektumot, és helyezze be a`groupShape` segítségével a dokumentumba`InsertNode` módszer.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## 6. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithShapes.AddGroupShape.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Példa forráskódra a Csoportalak hozzáadása az Aspose.Words segítségével .NET-hez 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Ez az! Sikeresen hozzáadott egy több alakzatot tartalmazó csoportalakzatot a Word-dokumentumhoz az Aspose.W segítségével