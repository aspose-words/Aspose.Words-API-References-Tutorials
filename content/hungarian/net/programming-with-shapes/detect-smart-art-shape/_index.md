---
title: Intelligens művészi alakzat észlelése
linktitle: Intelligens művészi alakzat észlelése
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan észlelheti a Smart Art alakzatokat Word-dokumentumban az Aspose.Words for .NET segítségével, amely grafikus ábrázolásokat azonosít.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/detect-smart-art-shape/
---

Ez az oktatóanyag elmagyarázza, hogyan észlelheti a Smart Art alakzatokat egy Word-dokumentumban az Aspose.Words for .NET használatával. Az intelligens művészeti formák olyan grafikus ábrázolások, amelyek az információk és ötletek vizuális megjelenítésére szolgálnak.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## 3. lépés: Intelligens művészi alakzatok észlelése
 Iteráljon a típus gyermekcsomópontjain keresztül`Shape` a dokumentumban a`GetChildNodes`módszer. Ellenőrizze, hogy az egyes alakzatokban van-e Smart Art a`HasSmart Art` ingatlan.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## 4. lépés: Írja ki az eredményt
Nyomtassa ki az alakzatok számát a dokumentumban észlelt Smart Art segítségével.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Példa forráskódra a Smart Art Shape észleléséhez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Ez az! Sikeresen észlelt Smart Art alakzatokat a Word-dokumentumban az Aspose.Words for .NET használatával.