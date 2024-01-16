---
title: Törölje a fejléc-lábléc tartalmát
linktitle: Törölje a fejléc-lábléc tartalmát
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan távolíthat el fejléc- és lábléctartalmat egy Word-dokumentumból az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-section/delete-header-footer-content/
---

Ebben az oktatóanyagban bemutatjuk, hogyan távolíthat el fejléc- és lábléctartalmat a Word-dokumentumból az Aspose.Words könyvtár segítségével a .NET-hez. A tartalom eltávolítása a fejlécekből és láblécekből akkor lehet hasznos, ha vissza szeretné állítani ezeket az elemeket, vagy eltávolítani szeretné a dokumentumból. Lépésről lépésre segítünk megérteni és megvalósítani a kódot a .NET-projektben.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár
- Az eltávolítani kívánt fejléceket és lábléceket tartalmazó Word-dokumentum

## 1. lépés: Határozza meg a dokumentumkönyvtárat
 Először is be kell állítania a könyvtár elérési útját a Word-dokumentum helyére. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot, és lépjen a szakaszra
 Ezután betöltjük a Word-dokumentumot a`Document` osztály. A dokumentum első részét a 0 index használatával érjük el.

```csharp
// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Document.docx");

// Nyissa meg a részt
Section section = doc.Sections[0];
```

## 3. lépés: Törölje a fejléc és a lábléc tartalmát
 A fejléc és lábléc tartalmának a szakaszból való eltávolításához a`ClearHeadersFooters` módszer.

```csharp
section.ClearHeadersFooters();
```

### Minta forráskód a fejléc lábléctartalmának törléséhez az Aspose.Words for .NET használatával 

```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Következtetés
Ebben az oktatóanyagban azt láthattuk, hogyan távolíthat el fejléc- és lábléctartalmat egy Word-dokumentumból az Aspose.Words for .NET használatával. A tartalom eltávolítása a fej- és láblécekből lehetővé teszi az adott elemek visszaállítását vagy eltávolítását a dokumentumból. Nyugodtan testreszabhatja és használhatja ezt a funkciót saját igényei szerint.

### GYIK a fejléc lábléc tartalmának törléséhez

#### K: Hogyan állíthat be dokumentumkönyvtárat az Aspose.Words for .NET-ben?

 V: A dokumentumokat tartalmazó könyvtár elérési útjának beállításához le kell cserélnie`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal. Íme, hogyan kell csinálni:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### K: Hogyan lehet betölteni a dokumentumot és a hozzáférési részt az Aspose.Words for .NET-ben?

 V: A Word-dokumentum betöltése a`Document` osztály hívott`doc` és a dokumentum első részét a 0 index használatával érheti el, a következő kódot használhatja:

```csharp
// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Document.docx");

// Nyissa meg a részt
Section section = doc.Sections[0];
```

#### K: Hogyan lehet eltávolítani a fejléc- és lábléctartalmat az Aspose.Words for .NET-ből?

 V: A fejléc és lábléc tartalmának a szakaszból való eltávolításához használja a`ClearHeadersFooters` módszer:

```csharp
section.ClearHeadersFooters();
```

#### K: Hogyan lehet elmenteni a módosított dokumentumot az Aspose.Words for .NET-be?

V: Miután törölte a fejléc és a lábléc tartalmát, a módosított dokumentumot a következő kóddal mentheti fájlba:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```