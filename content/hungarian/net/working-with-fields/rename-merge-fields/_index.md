---
title: Az Egyesítési mezők átnevezése
linktitle: Az Egyesítési mezők átnevezése
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan nevezheti át a dokumentum egyesített mezőit az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-fields/rename-merge-fields/
---

Íme egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET összevonási mező átnevezési funkcióját használja. Gondosan kövesse az egyes lépéseket a kívánt eredmény eléréséhez.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum létrehozása és az egyesítési mezők beillesztése

Kezdjük egy új dokumentum létrehozásával, és az a`DocumentBuilder` az egyesítési mezők beszúrásához.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## 3. lépés: Egyesítési mezők átnevezése

Végigpörgetjük a dokumentumtartomány minden egyes mezőjét, és ha összevont mezőről van szó, átnevezzük a mezőt a "_Átnevezett" utótag.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## 4. lépés: A dokumentum mentése

 Végül hívjuk a`Save()` módot a módosított dokumentum mentésére.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Példa a forráskódhoz az egyesítési mezők Aspose.Words for .NET-hez való átnevezésére

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozza létre a dokumentumot, és illessze be az egyesítési mezőket.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Az egyesítési mezők átnevezése.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Mentse el a dokumentumot.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Kövesse ezeket a lépéseket a dokumentum egyesítési mezőinek átnevezéséhez az Aspose.Words for .NET használatával.

### GYIK

#### K: Hogyan nevezhetem át az egyesített mezőket egy Word-dokumentumban az Aspose.Words for .NET használatával?

 V: A Word-dokumentum egyesített mezőinek átnevezéséhez az Aspose.Words for .NET használatával, a dokumentumban található mezők között lépkedhet a`FieldMergingArgs` osztályt, és használja a`FieldMergingArgs.FieldName` metódus a mező átnevezéséhez.

#### K: A Word-dokumentumban csak bizonyos egyesített mezőket lehet átnevezni az Aspose.Words for .NET segítségével?

V: Igen, csak bizonyos egyesített mezőket lehet átnevezni egy Word-dokumentumban az Aspose.Words for .NET segítségével. Szűrheti, hogy mely mezőket kívánja átnevezni meghatározott feltételekkel, például mezőnévvel vagy más releváns tulajdonságokkal. Ezután átnevezheti a megfelelő mezőket a`FieldMergingArgs.FieldName` módszer.

#### K: Hogyan ellenőrizhetem, hogy egy egyesített mező sikeresen át lett-e nevezve egy Word-dokumentumban az Aspose.Words for .NET segítségével?

 V: Ha ellenőrizni szeretné, hogy egy egyesített mező sikeresen át lett-e nevezve egy Word-dokumentumban az Aspose.Words for .NET segítségével, használja a`FieldMergedArgs` osztályt, és elérheti a`FieldMergedArgs.IsMerged` tulajdonságot annak meghatározására, hogy a mezőt a találattal átnevezték-e.

#### K: Milyen következményekkel jár, ha egy Word-dokumentum egyesített mezőjét Aspose.Words for .NET-re nevezi át?

V: Ha átnevez egy összevont mezőt egy Word-dokumentumban az Aspose.Words for .NET segítségével, megváltoztatja a mező nevét a dokumentumban, ami hatással lehet a mező nevétől függő egyéb funkciókra vagy folyamatokra. Az egyesített mezők átnevezése előtt feltétlenül vegye figyelembe ezeket a lehetséges következményeket.

#### K: Visszaállítható-e az egyesített mező eredeti neve, miután átnevezte az Aspose.Words for .NET-re?

V: Igen, visszaállítható az egyesített mező eredeti neve, miután átnevezte az Aspose.Words for .NET-re. A mező eredeti nevét eltárolhatja egy változóban vagy listában, majd szükség esetén felhasználhatja ezt az információt az eredeti név visszaállításához.