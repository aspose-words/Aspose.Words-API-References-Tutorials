---
title: Több szakasz
linktitle: Több szakasz
second_title: Aspose.Words Document Processing API
description: Tanulja meg, hogyan lehet lekérni és feldolgozni több szakaszból álló strukturált dokumentumcímkéket egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/multi-section/
---

Ez az oktatóanyag elmagyarázza, hogyan dolgozhat több szakaszból álló strukturált dokumentumcímkékkel egy Word-dokumentumban az Aspose.Words for .NET használatával. Lekérheti és feldolgozhatja a dokumentumban található szakaszcímkéket.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és töltse le a többrészes címkéket
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját. Az összes strukturált dokumentumcímke-tartomány kezdőcsomópontjának lekérése a dokumentumban a`GetChildNodes` módszer.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## 3. lépés: A többrészes címkék feldolgozása
Iteráljon a strukturált dokumentumcímke-tartomány kezdőcsomópontjainak gyűjteményén keresztül. Ebben a példában egyszerűen kinyomtatjuk az egyes címkék címét a konzolra. Igényei szerint további feldolgozást végezhet.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Példa forráskódra a Multi Section-hez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Ez az! Sikeresen lekérte és feldolgozta a több szakaszból álló strukturált dokumentumcímkéket a Word-dokumentumban az Aspose.Words for .NET segítségével.