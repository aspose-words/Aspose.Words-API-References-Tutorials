---
title: Mező beszúrása Szöveg beszúrása dokumentumkészítő nélkül
linktitle: FieldIncludeText beszúrása dokumentumkészítő nélkül
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be FieldIncludeText mezőt Word-dokumentumaiba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Az alábbiakban egy lépésről lépésre bemutatjuk a C# forráskódot, amely az Aspose.Words for .NET "FieldIncludeText mező beszúrása" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum és a bekezdés létrehozása

Kezdjük egy új dokumentum létrehozásával és egy bekezdés inicializálásával.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3. lépés: A FieldIncludeText mező beszúrása

 Használjuk a`AppendField()` metódussal beszúrhat egy FieldIncludeText mezőt a bekezdésbe.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Ezután konfiguráljuk a FieldIncludeText mező tulajdonságait a könyvjelző nevének és a forrásfájl nevének megadásával.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Ezután hozzáadjuk a bekezdést a dokumentum törzséhez.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Végül hívjuk a`Update()` módszer a mező frissítéséhez.

```csharp
fieldIncludeText.Update();
```

### Példa a forráskódra egy FieldIncludeText mező beszúrásához az Aspose.Words .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozd létre a dokumentumot és a bekezdést.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// FieldIncludeText mező beszúrása.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Ebben a példában létrehoztunk egy új dokumentumot, inicializáltunk egy bekezdést, beszúrtunk egy FieldIncludeTexten szöveget, amely megadja a könyvjelző nevét és a forrásfájl nevét, és elmentettük a dokumentumot egy megadott fájlnévvel.

Ezzel véget is értünk az "Insert a FieldIncludeText" funkció használatáról szóló útmutatónknak az Aspose.Words for.NET-hez.

### GYIK

#### K: Hogyan adhatom meg a forrásfájlt a szövegbeviteli mezőhöz az Aspose.Words for .NET-ben?

 V: Az Aspose.Words for .NET szövegbeillesztési mezőjének forrásfájljának megadásához használja a`FieldIncludeText.SourceFullName`tulajdonság a forrásfájl teljes elérési útjának beállításához. Győződjön meg arról, hogy a forrásfájl elérhető, és tartalmazza a szövegbeillesztési mezőbe felvenni kívánt tartalmat.

#### K: Az Aspose.Words for .NET segítségével beilleszthetek egy makróból származó szöveget a szövegfelvevő mezőbe?

 V: Igen, az Aspose.Words for .NET segítségével beilleszthet egy makróból származó szöveget a szövegfelvevő mezőbe. Használhatja a`FieldIncludeText.IncludeText` tulajdonság megadása annak a makrónak a nevének megadásához, amelynek a tartalmát szerepeltetni kell a mezőben.

#### K: Beszúrja a szöveget tartalmazó mezőt a dokumentumkészítő nélkül, befolyásolja a Word dokumentumszerkezetét az Aspose.Words for .NET használatával?

V: A szöveges mező beszúrása a dokumentumkészítő nélkül nem befolyásolja közvetlenül a Word dokumentum szerkezetét. Azonban egy új mezőelemet ad a dokumentum tartalmához. A dokumentum szerkezetét módosíthatja a meglévő elemek hozzáadásával, törlésével vagy módosításával az Ön igényei szerint.

#### K: Testreszabhatom a szövegbefoglaló mező megjelenését Word-dokumentumban az Aspose.Words for .NET segítségével?

V: A szövegmező felvétele nem szabja meg közvetlenül a megjelenését a Word-dokumentumban. A mellékelt szöveget azonban formázhatja az Aspose.Words for .NET-ben elérhető bekezdéstulajdonságokkal, betűtípustulajdonságokkal és egyéb formázási objektumokkal.