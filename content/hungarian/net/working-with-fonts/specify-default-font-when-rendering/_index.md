---
title: Adja meg az alapértelmezett betűtípust rendereléskor
linktitle: Adja meg az alapértelmezett betűtípust rendereléskor
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre az alapértelmezett betűtípus megadásához, amikor egy dokumentumot az Aspose.Words for .NET használatával jelenít meg.
type: docs
weight: 10
url: /hu/net/working-with-fonts/specify-default-font-when-rendering/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük az alapértelmezett betűtípus megadásához, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Ennek az oktatóanyagnak a végére tudni fogja, hogyan adjon meg egy alapértelmezett betűtípust a dokumentumok Aspose.Words for .NET használatával történő renderelésekor.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahová menteni szeretné a szerkesztett renderelt dokumentumot. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a renderelni kívánt dokumentumot
 Ezután be kell töltenie a dokumentumot, hogy a segítségével renderelje`Document` osztály. Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. lépés: Állítsa be az alapértelmezett betűtípust
 Most megadhatja a rendereléskor használandó alapértelmezett betűtípust a példány létrehozásával`FontSettings` osztály és beállítás a`DefaultFontName` tulajdona a`DefaultFontSubstitution` tiltakozik a`DefaultFontSubstitution` tárgy`SubstitutionSettings` nak,-nek`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## 4. lépés: Mentse el a renderelt dokumentumot
 Végül a renderelt dokumentumot fájlba mentheti a`Save()` módszere a`Document` osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Minta forráskód az alapértelmezett betűtípus megadása rendereléskor Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Ha az itt definiált alapértelmezett betűtípus nem található a renderelés során, akkor
// helyette a géphez legközelebbi betűtípust használjuk.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell megadni az alapértelmezett betűtípust egy dokumentum Aspose.Words for .NET használatával történő előállítása során. A részletes útmutató követésével könnyedén beállíthat egy alapértelmezett betűtípust a dokumentumok renderelésekor. Az Aspose.Words hatékony és rugalmas API-t kínál a szövegfeldolgozáshoz a dokumentumokban található betűtípusokkal. Ennek a tudásnak a birtokában ellenőrizheti és személyre szabhatja dokumentumai megjelenítését az Ön egyedi igényei szerint.

### GYIK

#### K: Hogyan adhatok meg alapértelmezett betűtípust az Aspose.Words PDF-formátumba konvertálásakor?

 V: Az Aspose.Words PDF-be konvertálásakor alapértelmezett betűtípus megadásához használhatja a`PdfOptions` osztályt, és állítsa be a`DefaultFontName`tulajdonság a kívánt betűtípus nevéhez.

#### K: Mi a teendő, ha az alapértelmezett betűtípus nem érhető el a PDF-be konvertáláskor?

V: Ha a megadott alapértelmezett betűtípus nem érhető el a PDF-be konvertáláskor, az Aspose.Words helyettesítő betűtípust használ a konvertált dokumentum szövegének megjelenítéséhez. Ez némi eltérést okozhat az eredeti betűtípus megjelenésében.

#### K: Megadhatok alapértelmezett betűtípust más kimeneti formátumokhoz, például DOCX vagy HTML?

V: Igen, megadhat egy alapértelmezett betűtípust más kimeneti formátumokhoz, például a DOCX-hez vagy a HTML-hez a megfelelő konverziós beállítások használatával és az egyes formátumokhoz tartozó tulajdonságok beállításával.

#### K: Hogyan ellenőrizhetem az Aspose.Words-ben megadott alapértelmezett betűtípust?

 V: Az Aspose.Words-ben megadott alapértelmezett betűtípus ellenőrzéséhez használja a`DefaultFontName` tulajdona a`PdfOptions` osztályt, és kérje le a beállított betűtípus nevét.

#### K: Megadható más alapértelmezett betűtípus a dokumentum egyes szakaszaihoz?

V: Igen, a dokumentum egyes szakaszaihoz más alapértelmezett betűtípust is megadhat az egyes szakaszokra jellemző formázási beállításokkal. Ehhez azonban az Aspose.Words funkcióival fejlettebb dokumentumkezelésre lenne szükség.