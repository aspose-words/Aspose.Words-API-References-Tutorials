---
title: Adja meg a területi beállítást a mező szintjén
linktitle: Adja meg a területi beállítást a mező szintjén
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhat meg mezőszintű lokalizációt Word dokumentumokban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/specify-locale-at-field-level/
---

Íme egy lépésről lépésre bemutatott útmutató a következő C# forráskód leírásához, amely lehetővé teszi a lokalizáció mezőszintű meghatározását az Aspose.Words for .NET szolgáltatással. A kód használata előtt győződjön meg arról, hogy az Aspose.Words könyvtárat belefoglalta a projektbe.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ügyeljen arra, hogy megadja a dokumentumkönyvtár megfelelő elérési útját, ahová a szerkesztett dokumentum mentésre kerül.

## 2. lépés: Hozzon létre egy dokumentumgenerátort

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Itt készítünk egy példányt a`DocumentBuilder` osztály, amely lehetővé teszi számunkra, hogy mezőket adjunk a dokumentumhoz.

## 3. lépés: Szúrjon be egy dátummezőt egy adott hellyel

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 A dokumentumgenerátort használjuk egy típusú mező beszúrására`FieldType.FieldDate` a dokumentumba. Beállításával a`LocaleId`tulajdonát`1049`, ennek a mezőnek az orosz lokalizációját adjuk meg.

## 4. lépés: Mentse el a módosított dokumentumot

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Végül elmentjük a módosított dokumentumot a megadott hellyel egy megadott fájlba.

### Minta forráskód mezőszintű lokalizáció meghatározásához az Aspose.Words for .NET segítségével

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Ez egy példa a forráskódra a honosítás mezőszintű meghatározásához egy dokumentumban az Aspose.Words for .NET használatával. Ezzel a kóddal dátummezőket illeszthet be bizonyos helyekkel a Word-dokumentumokban.

### GYIK

#### K: Hogyan adhatom meg a mezőszintű területi beállítást az Aspose.Words for .NET-ben?

 V: A területi beállítás megadásához mezőszinten az Aspose.Words for .NET-ben használja a`FieldOptions` osztály és annak`FieldLocale` tulajdonságot a kívánt terület beállításához. Például használhatja`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` a francia (Franciaország) területi beállítás megadásához.

#### K: Megadható-e más területi beállítás az Aspose.Words for .NET minden mezőjéhez?

 V: Igen, az Aspose.Words for .NET-ben minden mezőhöz más-más területi beállítást lehet megadni. Használhatja a`FieldOptions.FieldLocale` tulajdonságot egy adott mező létrehozása vagy frissítése előtt, hogy más területi beállítást rendeljen hozzá.

#### K: Hogyan szerezhetem be az Aspose.Words for .NET mezőjének jelenleg használt területi beállítását?

 V: Az Aspose.Words for .NET egyik mezőjének jelenleg használt területi beállításához használja a mező`Field.LocaleId` ingatlan. Ez lehetővé teszi a mezőhöz társított terület-azonosító beszerzését.