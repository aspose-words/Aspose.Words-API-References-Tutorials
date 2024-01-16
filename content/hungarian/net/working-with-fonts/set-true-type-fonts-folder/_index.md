---
title: Állítsa be a True Type Fonts mappát
linktitle: Állítsa be a True Type Fonts mappát
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a valódi betűtípusok mappa beállításához egy dokumentum Aspose.Words for .NET használatával történő renderelésekor.
type: docs
weight: 10
url: /hu/net/working-with-fonts/set-true-type-fonts-folder/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a valódi betűtípus mappa beállításának folyamatán, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Ennek az oktatóanyagnak a végén tudni fogja, hogyan adjon meg egy True Type betűtípusokat tartalmazó egyéni mappát, amelyet a dokumentumok Aspose.Words for .NET használatával történő megjelenítéséhez használ.

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

## 3. lépés: Állítsa be a True Type Fonts mappát
Mostantól megadhatja a rendereléskor használandó igaz típusú betűtípusok mappáját a példány létrehozásával`FontSettings` osztályban és a`SetFontsFolder()` módszer a betűtípusok mappa beállításához. Megadhat egy egyéni mappát, amely a True Type betűtípusokat tartalmazza. A második paraméter a`SetFontsFolder()` jelzi, hogy kíván-e keresni a megadott mappa almappáiban is.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## 4. lépés: Mentse el a renderelt dokumentumot
 Végül a renderelt dokumentumot fájlba mentheti a`Save()` módszere a`Document` osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Minta forráskód a Set True Type Fonts mappához az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Vegye figyelembe, hogy ez a beállítás felülír minden alapértelmezett betűtípus-forrást, amely alapértelmezés szerint keresett. Most csak ezekben a mappákban lesz keresve
// Betűtípusok a betűtípusok renderelésekor vagy beágyazásakor. Ha további fontforrást szeretne hozzáadni a rendszer betűtípus-forrásainak megtartása mellett, használja a FontSettings.GetFontSources és
// FontSettings.SetFontSources helyett
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Állítsa be a betűtípus beállításait
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthatja be a valódi betűtípusok mappáját, amikor egy dokumentumot az Aspose.Words for .NET használatával jelenít meg. A részletes útmutató követésével könnyedén megadhat egy True Type betűtípusokat tartalmazó egyéni mappát a dokumentumok renderelésekor. Az Aspose.Words hatékony és rugalmas API-t kínál a szövegfeldolgozáshoz a dokumentumokban található betűtípusokkal. Ezzel a tudással szabályozhatja és testreszabhatja a dokumentumok renderelésekor használt betűtípusokat az Ön egyedi igényei szerint.

### GYIK

#### K: Hogyan konfigurálhatom az Aspose.Words TrueType betűtípusok mappáját?

 V: Az Aspose.Words TrueType fonts mappájának konfigurálásához használhatja a`SetTrueTypeFontsFolder` módszere a`Fonts` osztály, amely megadja a TrueType betűtípusokat tartalmazó mappa helyét.

#### K: Milyen típusú betűtípusok tekinthetők TrueType betűtípusoknak?

V: A TrueType betűtípusok népszerű betűtípusok. Gyakran használják a Word dokumentumokban, és .ttf vagy .ttc fájlkiterjesztésük van.

#### K: Megadhatok több TrueType font mappát az Aspose.Wordsben?

V: Igen, több TrueType betűtípus mappát is megadhat az Aspose.Wordsben a`SetTrueTypeFontsFolder` módszere a`Fonts` osztályt a mappahelyek listájával.

#### K: Hogyan ellenőrizhetem az Aspose.Wordsben konfigurált TrueType betűtípusok mappáját?

 V: Az Aspose.Words konfigurált TrueType Fonts mappájának ellenőrzéséhez használja a`GetTrueTypeFontsFolder` módszere a`Fonts` osztályt, hogy megkapja a konfigurált TrueType Fonts mappa helyét.

#### K: Miért fontos az Aspose.Words TrueType fonts mappájának konfigurálása?

V: Az Aspose.Words TrueType fonts mappájának beállítása azért fontos, mert segít az Aspose.Wordsnak megtalálni a Word dokumentumok feldolgozásakor szükséges betűtípusokat. Ez biztosítja a dokumentumok formázásának és megjelenésének egységességét, még a különböző rendszerekben is.