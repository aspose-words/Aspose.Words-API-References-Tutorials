---
title: Szerezzen tényleges alakhatárpontokat
linktitle: Szerezzen tényleges alakhatárpontokat
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet lekérni egy alakzat tényleges határait pontokban (mértékegységben) egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Ez az oktatóanyag elmagyarázza, hogyan lehet lekérni egy alakzat tényleges határait pontokban (mértékegységben) egy Word-dokumentumban az Aspose.Words for .NET használatával. A határok az alakzat méretét és helyzetét jelzik a dokumentumon belül.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Hozzon létre egy új dokumentumot és DocumentBuildert
 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder`tiltakozik a dokumentummal való munkavégzésre.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Szúrjon be egy képalakot
 Használja a`InsertImage` módszere a`DocumentBuilder` objektum egy képforma beillesztéséhez a dokumentumba. Paraméterként adja meg a képfájl elérési útját.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## 3. lépés: Az aktuális alakhatárpontok lekérése
 Hozzáférés az alakzathoz`ShapeRenderer` használni a`GetShapeRenderer` módszer. Ezután kérje le az alakzat tényleges határait pontokban a segítségével`BoundsInPoints` ingatlan.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Példa forráskód a tényleges alakhatárpontok megszerzéséhez az Aspose.Words for .NET használatával 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Ez az! Sikeresen lekérte egy alakzat tényleges határait pontokban a Word-dokumentumban az Aspose.Words for .NET segítségével.