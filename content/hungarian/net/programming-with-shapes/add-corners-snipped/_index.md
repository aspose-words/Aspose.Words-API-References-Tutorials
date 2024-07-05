---
title: Adja hozzá a levágott sarkokat
linktitle: Adja hozzá a levágott sarkokat
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat hozzá levágott sarkokkal rendelkező alakzatot egy Word-dokumentumhoz az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-shapes/add-corners-snipped/
---

 Ez az oktatóanyag elmagyarázza, hogyan adhat hozzá levágott sarkokkal rendelkező alakzatot egy Word-dokumentumhoz az Aspose.Words for .NET használatával. A sarkok levágott alakja testreszabható és beilleszthető a segítségével`InsertShape` módszer.

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

## 3. lépés: Helyezze be a sarkok levágott alakját
 Használja a`InsertShape` módszere a`DocumentBuilder` objektumot levágott sarkokkal rendelkező alakzat beszúrásához. Adja meg az alakzat típusát (ebben az esetben`ShapeType.TopCornersSnipped`), és adja meg a kívánt méretet a formához.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## 4. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithShapes.AddCornersSnipped.docx" néven mentjük.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Példa forráskód az Add Corners Snippedhez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Ez az! Sikeresen hozzáadott egy sarkokkal levágott alakzatot a Word-dokumentumhoz az Aspose.Words for .NET segítségével.