---
title: Körlevél-címblokk mező beszúrása DOM használatával
linktitle: Körlevél-címblokk mező beszúrása DOM használatával
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be körlevél-címblokk mezőt Word-dokumentumaiba az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Íme egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "Körlevél-címblokk mezőjének beszúrása" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A Document és a DocumentBuilder létrehozása

Kezdjük egy új dokumentum létrehozásával és a DocumentBuilder inicializálásával.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: A kurzor mozgatása a bekezdésre

 A DocumentBuildert használjuk`MoveTo()` metódussal mozgathatja a kurzort arra a bekezdésre, ahová be akarjuk szúrni a körlevél címblokk mezőjét.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 4. lépés: A Körlevél-címblokk mező beszúrása

 A DocumentBuildert használjuk`InsertField()` metódussal egy körlevél-címblokk mezőt illeszthet be a bekezdésbe.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Ezután konfiguráljuk a címblokk mező tulajdonságait, megadva a megfelelő beállításokat, például az ország/régió nevének megadását, a cím formázását ország/régió szerint, az ország-/régiónevek kizárása, név- és címformátum, valamint nyelvazonosító.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Végül hívjuk a`Update()` módszer a mező frissítéséhez.

```csharp
field. Update();
```

### Minta forráskód egy körlevél-címblokk mező beszúrásához az Aspose.Words for .NET-hez

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// A következőhöz hasonló körlevél-címblokkot szeretnénk beszúrni:
// { CÍMBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { CÍMBLOCK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { CÍMBLOCK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { CÍMBLOCK \\c 1 \\d \\e Teszt2 }
field.ExcludedCountryOrRegionName = "Test2";

// { CÍMBLOCK \\c 1 \\d \\e Teszt2 \\f Teszt3 }
field.NameAndAddressFormat = "Test3";

// { CÍMBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### GYIK

#### K: Hogyan szabhatom testre a levelezési cím formátumát egy Word-dokumentumban az Aspose.Words for .NET segítségével?

 V: Testreszabhatja a levelezési cím formátumát egy Word-dokumentumban az Aspose.Words for .NET segítségével a`FieldAddressBlock`tárgy. A kívánt formátum eléréséhez beállíthatja a formázási beállításokat, például a címstílust, az elválasztókat, az opcionális elemeket stb.

#### K: Hogyan adhatom meg a forrásadatokat a levelezési cím mezőben az Aspose.Words for .NET-ben?

 V: Az Aspose.Words for .NET levelezési cím mezőjének forrásadatainak megadásához használja a`FieldAddressBlock.StartAddress` és`FieldAddressBlock.EndAddress` tulajdonságait. Ezek a tulajdonságok a külső adatforrásban, például CSV-fájlban, adatbázisban stb. található címtartományok meghatározására szolgálnak.

#### K: Az Aspose.Words for .NET segítségével választható elemeket is beilleszthetek a levelezési cím mezőbe?

 V: Igen, az Aspose.Words for .NET segítségével választható elemeket is megadhat a levelezési cím mezőben. Opcionális elemeket a segítségével határozhat meg`FieldAddressBlock.OmitOptional` metódus annak meghatározására, hogy be kell-e venni vagy kizárni az opcionális elemeket, például a címzett nevét, cégnevét stb.

#### K: A levelezési cím mező beszúrása a DOM használatával hatással van a Word dokumentumszerkezetére az Aspose.Words for .NET használatával?

V: Levelezési cím mező beszúrása a DOM használatával nem befolyásolja közvetlenül a Word dokumentum szerkezetét. Azonban egy új mezőelemet ad a dokumentum tartalmához. A dokumentum szerkezetét módosíthatja a meglévő elemek hozzáadásával, törlésével vagy módosításával az Ön igényei szerint.