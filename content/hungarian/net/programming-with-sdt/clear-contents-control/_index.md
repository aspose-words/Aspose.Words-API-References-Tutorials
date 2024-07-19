---
title: Tartalomszabályozás törlése
linktitle: Tartalomszabályozás törlése
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan törölheti a vezérlőelemek tartalmát egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/clear-contents-control/
---

Ez az oktatóanyag bemutatja, hogyan törölheti az SDT tartalmát egy Word-dokumentumban az Aspose.Words for .NET használatával. Az SDT tartalmának törlése eltávolít minden szöveget vagy gyermekcsomópontot a tartalomvezérlőn belül.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és szerezze be a StructuredDocumentTag-et
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját. Ezután szerezze be a kívántat`StructuredDocumentTag` dokumentumból. Ebben a példában feltételezzük, hogy az SDT a dokumentum első gyermekcsomópontja.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. lépés: Törölje a StructuredDocumentTag tartalmát
 Törölje az SDT tartalmát a gombbal`Clear` módszer. Ezzel eltávolítja a tartalomvezérlőn belüli szöveges vagy gyermek csomópontokat.

```csharp
sdt.Clear();
```

## 4. lépés: Mentse el a dokumentumot
 Mentse el a módosított dokumentumot a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.ClearContentsControl.doc" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Példa forráskód a Clear Contents Controlhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Ez az! Sikeresen törölte a Word-dokumentumban található StructuredDocumentTag tartalmát az Aspose.Words for .NET használatával.