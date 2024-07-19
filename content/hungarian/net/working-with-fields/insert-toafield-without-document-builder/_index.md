---
title: TOA mező beszúrása Dokumentumkészítő nélkül
linktitle: TOA mező beszúrása Dokumentumkészítő nélkül
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató a TOA mező beszúrásához Document Builder nélkül az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-toafield-without-document-builder/
---

Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "TOA Field Insertion" funkcióját használja. Gondosan kövesse az egyes lépéseket a kívánt eredmény eléréséhez.

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

## 3. lépés: A TA mező beszúrása

A FieldTA osztályt használjuk egy TA mező beillesztésére a bekezdésbe.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## 4. lépés: A bekezdés hozzáadása a dokumentum törzséhez

A TA mezőt tartalmazó bekezdést hozzáadjuk a dokumentum törzséhez.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 5. lépés: A TOA mező bekezdésének létrehozása

Létrehozunk egy új bekezdést a TOA mezőhöz.

```csharp
para = new Paragraph(doc);
```

## 6. lépés: A TOA mező beszúrása

A FieldToa osztályt használjuk egy TOA mező beillesztésére a bekezdésbe.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## 7. lépés: A bekezdés hozzáadása a dokumentum törzséhez

A TOA mezőt tartalmazó bekezdést hozzáadjuk a dokumentum törzséhez.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 8. lépés: Frissítse a TOA mezőt

 Végül hívjuk a`Update()` módszert a TOA mező frissítéséhez.

```csharp
fieldToa.Update();
```

### Forráskód-példa TOA mezőbeillesztéshez Document Builder nélkül az Aspose.Words for .NET-hez

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Ilyen TA és TOA mezőket szeretnénk beszúrni:
// { TA \c 1 \l "Érték 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### GYIK

#### K: Hogyan lehet testreszabni a Word dokumentumba beillesztett TOA mező megjelenését az Aspose.Words for .NET segítségével?

 V: Testreszabhatja a beszúrt TOA mező megjelenését a tulajdonságok használatával`FieldTOA` objektumot a formázási beállítások megadásához.

#### K: Hozzáadhatok több TOA mezőt egyetlen Word dokumentumhoz az Aspose.Words for .NET használatával?

V: Igen, az Aspose.Words for .NET használatával több TOA-mezőt is hozzáadhat egyetlen Word-dokumentumhoz. Csak ismételje meg a beszúrási lépéseket minden mezőnél.

#### K: Hogyan ellenőrizhetem, hogy az Aspose.Words for .NET segítségével sikeresen beszúrt-e egy TOA mezőt egy Word dokumentumba?

V: A TOA-mező sikeres beszúrásának ellenőrzéséhez böngészhet a dokumentum tartalmában, és kereshet TOA-mezőpéldányokat.

#### K: A TOA mező beszúrása a DocumentBuilder használata nélkül hatással van a Word dokumentum formázására az Aspose.Words for .NET használatával?

V: A TOA mező beszúrása a DocumentBuilder használata nélkül nincs közvetlen hatással a Word dokumentum formázására. A TOA mező formázási beállításai azonban hatással lehetnek a dokumentum általános formázására.