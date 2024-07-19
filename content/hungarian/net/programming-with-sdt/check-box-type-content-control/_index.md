---
title: Jelölőnégyzet típusa Tartalomvezérlés
linktitle: Jelölőnégyzet típusa Tartalomvezérlés
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre jelölőnégyzet típusú tartalomvezérlőt Word-dokumentumban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-sdt/check-box-type-content-control/
---

Ez az oktatóanyag elmagyarázza, hogyan hozhat létre jelölőnégyzet típusú tartalomvezérlőt Word-dokumentumban az Aspose.Words for .NET használatával. A jelölőnégyzet tartalomvezérlői lehetővé teszik a felhasználók számára, hogy bejelöljenek vagy töröljenek egy jelölőnégyzetet a dokumentumon belül.

## Előfeltételek
Az oktatóanyag követéséhez a következőkre van szükség:

- Aspose.Words for .NET könyvtár telepítve.
- C# és Word dokumentumokkal végzett szövegszerkesztési alapismeretek.

## 1. lépés: Állítsa be a dokumentumkönyvtárat
 Kezdje a dokumentumkönyvtár elérési útjának beállításával. Cserélje ki`"YOUR DOCUMENT DIRECTORY"`annak a könyvtárnak a tényleges elérési útjával, ahová a dokumentumot menteni szeretné.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumot és a DocumentBuildert
 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder` a dokumentum tartalmának felépítéséhez.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Adjon hozzá egy jelölőnégyzetet típusú tartalomvezérlőt
 Hozzon létre egy`StructuredDocumentTag` val vel`SdtType.Checkbox` hogy képviselje a jelölőnégyzet tartalomvezérlőjét. Adja meg`MarkupLevel.Inline` hogy elhelyezze a szövegben.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## 4. lépés: Mentse el a dokumentumot
 Mentse a dokumentumot a megadott könyvtárba a`Save`módszer. Adja meg a kívánt fájlnevet a megfelelő fájlkiterjesztéssel. Ebben a példában a dokumentumot "WorkingWithSdt.CheckBoxTypeContentControl.docx" néven mentjük.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Példa forráskódra a jelölőnégyzet típusú tartalomvezérléshez az Aspose.Words for .NET használatával 

```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Ez az! Sikeresen létrehozott egy jelölőnégyzet típusú tartalomvezérlőt a Word-dokumentumban az Aspose.Words for .NET használatával.