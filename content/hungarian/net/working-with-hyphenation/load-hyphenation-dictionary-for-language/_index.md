---
title: Elválasztási szótár betöltése a nyelvhez
linktitle: Elválasztási szótár betöltése a nyelvhez
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan tölthet be elválasztási szótárt egy adott nyelvhez az Aspose.Words for .NET alkalmazásban.
type: docs
weight: 10
url: /hu/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

Ebben a lépésenkénti oktatóanyagban megmutatjuk, hogyan tölthet be egy elválasztási szótárt egy adott nyelvhez az Aspose.Words for .NET-be. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és konfigurálva van a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A dokumentum betöltése

Először töltse be a dokumentumot a megadott könyvtárból:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2. lépés: Az elválasztási szótár betöltése

Ezután nyisson meg egy adatfolyamot az elválasztási szótárfájlhoz, és mentse el a kívánt nyelvre. Ebben a példában a svájci német (de-CH) szótárat töltjük be:

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Győződjön meg arról, hogy a megfelelő szótárfájl van az adatkönyvtárában.

## 3. lépés: Mentse el a módosított dokumentumot

Végül mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Így ! Sikeresen betöltött egy elválasztási szótárt egy adott nyelvhez az Aspose.Words for .NET-ben.

### Példa forráskód elválasztási szótár betöltésére egy nyelvhez az Aspose.Words for .NET használatával

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Nyugodtan használhatja ezt a kódot saját projektjeiben, és módosíthatja sajátos igényei szerint.

### GYIK

#### K: Hogyan tölthető be egy szótagozási szótár egy adott nyelvhez az Aspose.Words-ben?

 V: Ha az Aspose.Words-ben egy adott nyelvhez szeretne szótagozási szótárt betölteni, használja a`Hyphenation` osztály és a`LoadDictionary()` módszer. Hozzon létre egy példányt a`Hyphenation` osztályt, és hívja fel a`LoadDictionary()` metódus, amely megadja a szótagozási szótárfájl elérési útját a kívánt nyelvhez. Ez betölti a szótagozási szótárt az Aspose.Words-be.

#### K: Hol találok szótagozási szótár fájlokat a különböző nyelvekhez?

V: Különféle online forrásokban találhat szótagozási szótár fájlokat különböző nyelvekhez. Ezek a fájlok általában XML vagy TEX formátumúak. Nyílt forráskódú szótagozási szótárakat találhat különböző nyelvekhez a nyelvészeti projekteknek vagy forráskód-tárházaknak szentelt webhelyeken.

#### K: Hogyan alkalmazhatom a betöltött szótagszótárt egy dokumentumra az Aspose.Words programban?

V: Ha a betöltött szótagozási szótárt egy dokumentumra szeretné alkalmazni az Aspose.Words programban, ismételje meg a szavakat a dokumentumban, és használja a`Hyphenate()` módszere a`Hyphenation` osztályban, hogy megkapjuk a szavak szótagolását. Ezután szükség szerint formázhatja a szótagozott szavakat, például kötőjelek hozzáadásával a szótagok közé.

#### K: Milyen nyelveken támogatott az Aspose.Words szótagosítása?

V: Az Aspose.Words több nyelven támogatja a szótagosítást, beleértve az angol, francia, spanyol, német, olasz, holland, orosz, portugál, svéd, norvég, dán, finn, lengyel, cseh és még sok más nyelvet. Tekintse meg az Aspose.Words dokumentációját a szótagozáshoz támogatott nyelvek teljes listájáért.