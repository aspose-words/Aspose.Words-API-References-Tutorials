---
title: Állítsa be a Tartalomvezérlő színét
linktitle: Állítsa be a Tartalomvezérlő színét
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be egy tartalomvezérlő színét egy Word-dokumentumban az Aspose.Words for .NET használatával, testreszabva a megjelenését.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/set-content-control-color/
---

Ez az oktatóanyag elmagyarázza, hogyan állíthatja be a tartalomvezérlő színét egy Word-dokumentumban az Aspose.Words for .NET használatával. Testreszabhatja a tartalomvezérlők megjelenését a színük megváltoztatásával.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és töltse le a tartalomvezérlőt
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját. Töltse le a kívánt tartalomvezérlőt a dokumentumból. Ebben a példában feltételezzük, hogy a tartalomvezérlő az első strukturált dokumentumcímke a dokumentumban.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. lépés: Állítsa be a Tartalomvezérlő színét
 Állítsa be a tartalomvezérlő színét a hozzárendelésével`Color` értéket a`Color` a strukturált dokumentumcímke tulajdonsága. Ebben a példában a színt pirosra állítottuk.

```csharp
sdt.Color = Color.Red;
```

## 4. lépés: Mentse el a dokumentumot
 Mentse el a módosított dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.SetContentControlColor.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Példa forráskódra a Set Content Control Color funkcióhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Ez az! Sikeresen beállította egy tartalomvezérlő színét a Word-dokumentumban az Aspose.Words for .NET segítségével.