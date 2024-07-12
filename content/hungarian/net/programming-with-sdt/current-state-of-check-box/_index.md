---
title: A jelölőnégyzet jelenlegi állapota
linktitle: A jelölőnégyzet jelenlegi állapota
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kérheti le és állíthatja be a jelölőnégyzet tartalomvezérlőjének aktuális állapotát egy Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/current-state-of-check-box/
---

Ez az oktatóanyag elmagyarázza, hogyan lehet lekérni és beállítani egy jelölőnégyzet tartalomvezérlőjének aktuális állapotát egy Word-dokumentumban az Aspose.Words for .NET használatával. A jelölőnégyzetet bejelölheti vagy törölheti az aktuális állapota alapján.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak a tényleges elérési útjával, ahol a dokumentum található.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és töltse le a tartalomvezérlő jelölőnégyzetet
 Töltse be a Word dokumentumot a`Document` konstruktor, paraméterként átadva a dokumentum elérési útját. Ezután kérje le a kívánt jelölőnégyzet tartalomvezérlőjét a dokumentumból. Ebben a példában feltételezzük, hogy a jelölőnégyzet az első strukturált dokumentumcímke a dokumentumban.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 3. lépés: Jelölje be vagy törölje a jelölőnégyzetet az aktuális állapota alapján
 Ellenőrizze, hogy a beolvasott strukturált dokumentum címke típusú-e`SdtType.Checkbox` . Ha igen, állítsa be a`Checked` a tartalomvezérlő tulajdonsága`true` hogy jelölje be a négyzetet. Ellenkező esetben hagyhatja bejelöletlenül.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## 4. lépés: Mentse el a dokumentumot
 Mentse el a módosított dokumentumot a megadott könyvtárba a`Save` módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.CurrentStateOfCheckBox.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Példa a Current State Of Check Box forráskódjához az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Szerezze be az első tartalomvezérlőt a dokumentumból.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Ez az! Sikeresen letöltötte és beállította egy jelölőnégyzet tartalomvezérlőjének jelenlegi állapotát a Word-dokumentumban az Aspose.Words for .NET használatával.