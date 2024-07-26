---
title: Combo Box Content Control
linktitle: Combo Box Content Control
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre Combo Box tartalomvezérlőt Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/combo-box-content-control/
---

Ez az oktatóanyag elmagyarázza, hogyan hozhat létre kombi tartalomvezérlőt Word-dokumentumban az Aspose.Words for .NET használatával. A kombinált tartalomvezérlők segítségével a felhasználók kiválaszthatnak egy elemet a legördülő listából.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumot és egy StructuredDocumentTag-et
 Hozzon létre egy új példányt a`Document` osztály és a`StructuredDocumentTag` a kombinált tartalomvezérlő megjelenítéséhez. Adja meg`SdtType.ComboBox` mint a típus és`MarkupLevel.Block` jelölési szintként egy blokkszintű kombinált doboz létrehozásához.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## 3. lépés: Tételek hozzáadása a kombinált mezőhöz
 Adjon hozzá elemeket a kombinált mezőhöz a gombbal`ListItems` tulajdona a`StructuredDocumentTag` . Minden elemet egy`SdtListItem` objektum, amely egy megjelenített szöveget és egy értéket vesz fel. Ebben a példában három elemet adunk a kombinált mezőhöz.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## 4. lépés: Adja hozzá a StructuredDocumentTag-et a dokumentumhoz
 A kombinált tartalomvezérlőt hozzáfűzi a dokumentum törzséhez a gombbal`AppendChild` a dokumentum első szakaszának törzsének módszere.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## 5. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.ComboBoxContentControl.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Példa forráskód a Combo Box Content Controlhoz az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Ez az! Sikeresen létrehozott egy kombinált tartalomvezérlőt a Word-dokumentumban az Aspose.Words for .NET használatával.