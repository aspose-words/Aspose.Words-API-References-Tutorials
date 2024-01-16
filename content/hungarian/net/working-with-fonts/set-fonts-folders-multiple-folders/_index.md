---
title: Betűtípusok beállítása Mappák Több mappa
linktitle: Betűtípusok beállítása Mappák Több mappa
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre több betűtípus-mappa beállításához, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel.
type: docs
weight: 10
url: /hu/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a több betűtípus-mappa beállításának folyamatán, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Ennek az oktatóanyagnak a végére tudni fogja, hogyan adhat meg több betűtípus-mappát a dokumentumok Aspose.Words for .NET használatával történő renderelésekor.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahová menteni szeretné a szerkesztett renderelt dokumentumot. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a renderelni kívánt dokumentumot
 Ezután betöltheti a dokumentumot a megjelenítéshez a`Document` osztály. Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. lépés: Állítsa be a betűtípus-mappákat
 Mostantól több betűtípus mappát is beállíthat a segítségével`FontSettings` osztály és a`SetFontsFolders()` módszer. Megadhatja a tömbben használni kívánt betűtípusmappák elérési útját. Ebben a példában két betűtípus mappát adtunk meg: "C:\MyFonts\" és "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## 4. lépés: Alkalmazza a betűtípusbeállításokat
 Ezután alkalmaznia kell a betűtípus-beállításokat a dokumentumban a`FontSettings` tulajdona a`Document` osztály.

```csharp
doc.FontSettings = fontSettings;
```

## 5. lépés: Mentse el a renderelt dokumentumot
 Végül a renderelt dokumentumot fájlba mentheti a`Save()` módszere a`Document` osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Minta forráskód a Set Fonts Folders Multiple Folders funkcióhoz az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Vegye figyelembe, hogy ez a beállítás felülír minden alapértelmezett betűtípus-forrást, amely alapértelmezés szerint keresett. Most csak ezekben a mappákban lesz keresve
// betűtípusok renderelésekor vagy beágyazásakor. Ha további fontforrást szeretne hozzáadni a rendszer betűtípus-forrásainak megtartása mellett, használja a FontSettings.GetFontSources és
// FontSettings.SetFontSources helyett.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthat be több betűtípus-mappát egy dokumentum Aspose.Words for .NET használatával történő előállítása során. A részletes útmutató követésével könnyedén megadhat több betűtípus-mappát a dokumentumok renderelésekor. Az Aspose.Words hatékony és rugalmas API-t kínál a szövegfeldolgozáshoz a dokumentumokban található betűtípusokkal. Ezzel a tudással szabályozhatja és testreszabhatja a dokumentumok renderelésekor használt betűtípusokat az Ön egyedi igényei szerint.

### GYIK

#### K: Hogyan állíthatok be több betűtípus-mappát az Aspose.Words-ben?

 V: Több betűtípus-mappa beállításához az Aspose.Words alkalmazásban használhatja a`SetFontsFolders` módszere a`Fonts` osztály, amely az egyéni betűtípus-mappahelyek listáját tartalmazza.

#### K: A több betűtípus mappa beállítása hatással van az Aspose.Words programmal feldolgozott összes dokumentumra?

V: Igen, a több betűtípus mappa beállítása az Aspose.Words programmal feldolgozott összes dokumentumot érinti. Miután meghatározta a betűtípus mappákat, az Aspose.Words ezeket a helyeket fogja használni a betűtípusok kereséséhez az összes dokumentumban.

#### K: Hány font mappát definiálhatok az Aspose.Words-ben?

V: Az Aspose.Words-ben tetszőleges számú betűtípus-mappát definiálhat. A meghatározható betűtípusmappák számának nincs konkrét korlátozása.

#### K: Hogyan ellenőrizhetem az Aspose.Words-ben meghatározott betűtípus-mappákat?

 V: Az Aspose.Words-ben meghatározott betűtípus-mappák ellenőrzéséhez használhatja a`GetFolders` módszere a`Fonts` osztályba, hogy megkapja a konfigurált font mappák helyét.

#### K: A font mappáknak tartalmazniuk kell bizonyos betűtípusokat?

V: Igen, a betűtípusmappáknak tartalmazniuk kell a Word-dokumentumokban használni kívánt betűtípusokat. Az Aspose.Words a dokumentumok feldolgozása során fontokat keres a megadott mappákban.