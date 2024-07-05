---
title: Nyelvek szavai kötőjellel
linktitle: Nyelvek szavai kötőjellel
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan lehet elválasztani szavakat különböző nyelveken Word-dokumentumokban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-hyphenation/hyphenate-words-of-languages/
---

Ebben a lépésről lépésre bemutatott oktatóanyagban bemutatjuk, hogyan kötőjelezhet el szavakat különböző nyelveken Word-dokumentumokban az Aspose.Words for .NET használatával. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és konfigurálva van a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat a hivatalos webhelyről.

## 1. lépés: A dokumentumobjektum inicializálása

 Először inicializálja a`Document` objektumot a különböző nyelvű szöveget tartalmazó forrásdokumentum elérési útjának megadásával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2. lépés: Elválasztási szótárak mentése

Ezután mentse el az elválasztási szótárakat a feldolgozni kívánt különböző nyelvekhez. Ebben a példában az amerikai angol és a svájci német szótárait regisztráljuk:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Győződjön meg arról, hogy a megfelelő szótárfájlok vannak az adatkönyvtárban.

## 3. lépés: Szavak feldolgozása elválasztással

Most már használhatja az elválasztási funkciókat a különböző nyelvű szavak feldolgozásához. Különféle módszereket használhat`Document` vagy`DocumentBuilder` egyedi igényeitől függően.

```csharp
// Példa: A DocumentBuilder elválasztási módszerének használata
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## 4. lépés: Mentse el a dokumentumot

Végül mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Így ! Sikeresen feldolgozta a szavakat az Aspose.Words for .NET segítségével, különböző nyelveken elválasztó szavakkal egy Word-dokumentumban.

### Minta forráskód a szó elválasztásához az Aspose.Words for .NET használatával

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Nyugodtan használhatja ezt a kódot saját projektjeiben, és módosíthatja sajátos igényei szerint.

### GYIK

#### K: Hogyan lehet egy szót egy adott nyelven szótagolni az Aspose.Words segítségével?

 V: Egy adott nyelv szótagozásához az Aspose.Words segítségével használhatja a`Hyphenation` osztály és a`Hyphenate()` módszer. Hozzon létre egy példányt a`Hyphenation` osztályt megadva a kívánt nyelvet, majd hívja meg a`Hyphenate()` módszer, amely argumentumként adja át a szót a szótagolásnak. Ez megadja a szó szótagjait a megadott nyelven.

#### K: Milyen nyelvi kódokat kell használni az Aspose.Words szótagozási nyelvének megadásához?

V: Az Aspose.Words szótagozási nyelvének megadásához a megfelelő nyelvi kódokat kell használnia. Használhatja például az "en"-t az angolhoz, az "fr"-t a franciához, az "es"-t a spanyolhoz, a "de"-t némethez stb. A támogatott nyelvkódok teljes listáját az Aspose.Words dokumentációban találja.

#### K: Az Aspose.Words összes nyelvén működik a szótagosítás?

V: Az Aspose.Words szótagosítása a nyelvspecifikus szótagképzési szabályoktól függ. Bár az Aspose.Words nyelvek széles skáláját támogatja, előfordulhat, hogy egyes nyelvek nem támogatottak, vagy előfordulhat, hogy a szótagozás nem érhető el számukra. Tekintse meg az Aspose.Words dokumentációját, hogy megtudja, mely nyelveken támogatott a szótagosítás.