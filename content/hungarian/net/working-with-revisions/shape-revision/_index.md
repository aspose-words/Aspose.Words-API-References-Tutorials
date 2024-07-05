---
title: Alak felülvizsgálata
linktitle: Alak felülvizsgálata
second_title: Aspose.Words Document Processing API
description: A Word-dokumentum alakzatainak átdolgozása az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-revisions/shape-revision/
---

Ebben a lépésenkénti útmutatóban végigvezetjük, hogyan módosíthatja az alakzatokat egy Word-dokumentumban az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum létrehozása és alakzatok hozzáadása

Az első lépés egy új dokumentum létrehozása és alakzatok hozzáadása.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 2. lépés: Kövesse nyomon a változatokat, és adjon hozzá egy másik alakzatot

Bekapcsoljuk a revíziókövetést, és hozzáadunk egy másik alakzatot.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 3. lépés: Szerezze be az alakzatgyűjteményt, és ellenőrizze a revíziókat

Lekérjük az alakzatok gyűjteményét a dokumentumból, és ellenőrizzük az egyes alakzatokhoz tartozó változatokat.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## 4. lépés: Az alakmozgatási változatok ellenőrzése

Be fogunk tölteni egy meglévő dokumentumot, amely alakeltolódási változatokat tartalmaz, és ellenőrizni fogjuk a kapcsolódó változatokat.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Példa a Shape Revision forráskódjához az Aspose.Words for .NET használatával

Itt található a teljes forráskód a dokumentum alakzatainak módosításához az Aspose.Words for .NET használatával:

```csharp
Document doc = new Document();

//Szúrjon be egy soros alakzatot a revíziók követése nélkül.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Kezdje el követni a változatokat, majd szúrjon be egy másik alakzatot.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Szerezze be a dokumentum alakzatgyűjteményét, amely csak az általunk hozzáadott két alakzatot tartalmazza.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Távolítsa el az első formát.
shapes[0].Remove();

// Mivel eltávolítottuk az alakzatot a változások követése közben, az alakzat törlési változatnak számít.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// És beszúrtunk egy másik alakzatot a változások követése közben, így ez az alakzat beszúrási változatnak számít.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// A dokumentumnak egy alakzata van, amelyet áthelyeztek, de az alakmozgatási változatokban ennek az alakzatnak két példánya lesz.
// Az egyik az érkezési helyén lévő alakzat, a másik pedig az eredeti helyén lévő alakzat lesz.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Ez a revízióhoz való lépés, egyben az érkezési cél alakzata is.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Ez az elmozdulás a revízióból, ami az eredeti helyén lévő alakzat.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet Word-dokumentumban lévő alakzatokat módosítani az Aspose.Words for .NET használatával. A dokumentum létrehozásának lépéseit követve, a revíziókövetés engedélyezésével, az egyes alakzatokhoz tartozó revíziók ellenőrzésével és az alakzatok mozgatásához szükséges revíziók ellenőrzésével sikeresen tudtuk kezelni a revíziókat. Az Aspose.Words for .NET hatékony API-t kínál a szövegfeldolgozáshoz Word-dokumentumokban található áttekintésekkel és űrlapokkal.

### GYIK

#### K: Hogyan tudok új dokumentumot létrehozni és alakzatokat hozzáadni az Aspose.Words for .NET-hez?

V: Új dokumentum létrehozásához és alakzatok hozzáadásához az Aspose.Words for .NET-ben a következő kódot használhatja. Itt adunk hozzá két alakzatot, egy kockát és egy napot a dokumentum első részéhez:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### K: Hogyan engedélyezhetem a revíziókövetést az Aspose.Words for .NET-ben?

 V: A revíziókövetés engedélyezéséhez az Aspose.Words for .NET-ben a`StartTrackRevisions` módszere a`Document` tárgy. Ez a metódus a revíziók szerzőjének nevét veszi paraméterként:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### K: Hogyan ellenőrizhetem az egyes alakzatokhoz tartozó változatokat egy Aspose.Words for .NET dokumentumban?

V: Az Aspose.Words for .NET dokumentumban lévő egyes alakzatokhoz tartozó változatok ellenőrzéséhez a dokumentum alakzatgyűjteményét a`GetChildNodes` módszerrel a`NodeType.Shape` csomópont típusa. Ezután elérheti az egyes alakzatokat`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , és`IsMoveToRevision` tulajdonságok az alakzathoz társított revízió típusának meghatározásához:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### K: Hogyan ellenőrizhetem az Aspose.Words for .NET dokumentumban lévő alakzatok eltolási változatait?

 V: Ha egy Aspose.Words for .NET-dokumentumban szeretné ellenőrizni az alakeltolódás-revíziókat, betölthet egy meglévő dokumentumot, amely alakeltolódás-változatokat tartalmaz. Ezután elérheti az egyes alakzatokat`IsMoveFromRevision` és`IsMoveToRevision` tulajdonságai annak meghatározásához, hogy áthelyezik-e, és ha igen, honnan és hová:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```