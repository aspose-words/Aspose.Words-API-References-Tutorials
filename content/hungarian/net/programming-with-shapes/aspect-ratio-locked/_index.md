---
title: Képarány zárolva
linktitle: Képarány zárolva
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan zárolható vagy oldható fel egy alakzat képaránya Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/aspect-ratio-locked/
---

Ez az oktatóanyag elmagyarázza, hogyan zárolható vagy oldható fel egy alakzat képaránya Word-dokumentumban az Aspose.Words for .NET használatával. A képarány rögzítésével megőrizheti az alakzat eredeti arányait az átméretezés során.

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
 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder`tiltakozik a dokumentummal való munkavégzésre.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Szúrjon be egy képalakot
 Használja a`InsertImage` módszere a`DocumentBuilder` objektum egy képforma beillesztéséhez a dokumentumba. Paraméterként adja meg a képfájl elérési útját.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 4. lépés: A képarány zárolása vagy feloldása
 Állítsa be a`AspectRatioLocked` az alakzat tulajdonsága ahhoz`true` vagy`false` a képarány zárolásához vagy feloldásához.

```csharp
shape.AspectRatioLocked = false; //Oldja fel a képarányt
```

## 5. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithShapes.AspectRatioLocked.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Példa forráskódra az Aspose.Words for .NET használatával zárolt képarányhoz 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Ez az! Sikeresen zárolta vagy feloldotta egy alakzat képarányát a Word-dokumentumban az Aspose.Words for .NET segítségével.