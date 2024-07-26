---
title: Függőleges horgony
linktitle: Függőleges horgony
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan helyezhet el egy alakzatot függőlegesen a dokumentumon belül az Aspose.Words for .NET függőleges rögzítési funkciójával.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/vertical-anchor/
---

Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.Words for .NET függőleges rögzítési funkcióját egy alakzat függőleges elhelyezéséhez a dokumentumon belül. Egy alakzat függőleges horgony tulajdonságának beállításával szabályozhatja annak függőleges igazítását a szöveghez vagy az oldalhoz.

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

## 3. lépés: Alakzat beszúrása és konfigurálása
 Szúrjon be egy alakzatot a dokumentumba a gombbal`InsertShape` módszere a`DocumentBuilder` tárgy. Állítsa be az alakzat kívánt méreteit.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## 4. lépés: Állítsa be a függőleges horgonyt
Állítsa be az alakzat függőleges rögzítési tulajdonságát a függőleges igazítás szabályozásához. Ebben a példában az "Alul" értékre állítjuk, hogy az alakzatot a szöveg vagy oldal alján rögzítsük.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## 5. lépés: Adjon hozzá tartalmat az alakzathoz
 Használja a`MoveTo` módszere a`DocumentBuilder` objektumot, hogy a kurzort az alakzat első bekezdésére vigye. Ezután használja a`Write` módszer tartalom hozzáadására az alakzathoz.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## 6. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithShapes.VerticalAnchor.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Példa a Vertical Anchor forráskódjához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Ez az! Sikeresen használta az Aspose.Words for .NET függőleges rögzítési funkcióját egy alakzat függőleges elhelyezésére a dokumentumon belül.