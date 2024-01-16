---
title: Frissítse a Smart Art rajzot
linktitle: Frissítse a Smart Art rajzot
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan frissítheti a Smart Art rajzot Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/update-smart-art-drawing/
---

Ez az oktatóanyag elmagyarázza, hogyan frissítheti a Smart Art rajzot Word-dokumentumban az Aspose.Words for .NET használatával. A dokumentumban lévő alakzatok iterációjával és annak ellenőrzésével, hogy van-e bennük Smart Art, frissítheti a Smart Art rajzot, hogy tükrözze az adatain végzett bármilyen változást.

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
Töltse be a Smart Art rajzot tartalmazó Word-dokumentumot a`Document` osztályú konstruktőr.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## 3. lépés: Frissítse a Smart Art rajzot
 Iteráljon a dokumentumban lévő alakzatokon keresztül a`GetChildNodes` módszerrel a`NodeType.Shape` paraméter. Ellenőrizze, hogy az egyes alakzatokban van-e Smart Art a`HasSmartArt` ingatlant, és ha igaz, hívja a`UpdateSmartArtDrawing` módszer a Smart Art rajz frissítéséhez.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Példa forráskód a Smart Art rajz frissítéséhez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Ez az! Sikeresen frissítette a Smart Art rajzot a Word-dokumentumban az Aspose.Words for .NET használatával.