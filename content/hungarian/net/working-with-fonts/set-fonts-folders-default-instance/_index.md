---
title: Állítsa be a Fonts Folders alapértelmezett példányát
linktitle: Állítsa be a Fonts Folders alapértelmezett példányát
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre az alapértelmezett betűtípusmappa beállításához, amikor egy dokumentumot Aspose.Words for .NET használatával renderel le.
type: docs
weight: 10
url: /hu/net/working-with-fonts/set-fonts-folders-default-instance/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük az alapértelmezett betűtípusmappa beállításának folyamatán, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén tudni fogja, hogyan állíthatja be a dokumentumok Aspose.Words for .NET használatával történő megjelenítéséhez használt alapértelmezett betűtípus-mappát.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahová menteni szeretné a szerkesztett renderelt dokumentumot. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Állítsa be az alapértelmezett betűtípusmappát
 Ezután beállíthatja az alapértelmezett betűtípus mappát a`FontSettings.DefaultInstance` osztály és a`SetFontsFolder()`módszer. Adja meg az alapértelmezett mappaként használni kívánt fonts mappa elérési útját.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## 3. lépés: Töltse be a renderelni kívánt dokumentumot
 Most betöltheti a dokumentumot renderelni a`Document` osztály. Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4. lépés: Mentse el a renderelt dokumentumot
 Végül a renderelt dokumentumot fájlba mentheti a`Save()` módszere a`Document` osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Minta forráskód a Set Fonts Folders alapértelmezett példányához az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthatja be az alapértelmezett betűtípus-mappát egy dokumentum Aspose.Words for .NET használatával történő renderelésekor. A lépésenkénti útmutató követésével egyszerűen megadhatja, hogy melyik betűtípus-mappa legyen alapértelmezett mappa a dokumentumok renderelésekor. Az Aspose.Words hatékony és rugalmas API-t kínál a szövegfeldolgozáshoz a dokumentumokban található betűtípusokkal. Ezzel a tudással szabályozhatja és testreszabhatja a dokumentumok renderelésekor használt betűtípusokat az Ön egyedi igényei szerint.

### GYIK

#### K: Hogyan állíthatok be alapértelmezett betűtípus-mappákat az Aspose.Words-ben?

 V: Az Aspose.Words alapértelmezett betűtípus-mappáinak beállításához használja a`Fonts` osztály és a`SetFontsFolders` módszer az egyéni betűtípusmappa-helyek megadásához.

#### K: Az alapértelmezett betűtípusmappák beállítása hatással van az Aspose.Wordddel feldolgozott összes Word dokumentumra?

V: Igen, az alapértelmezett betűtípusmappák beállítása az Aspose.Wordddel feldolgozott összes Word dokumentumot érinti. Miután beállította az alapértelmezett betűtípusmappákat, az Aspose.Words ezeket a helyeket fogja használni a betűtípusok kereséséhez az összes dokumentumban.

#### K: Beállíthatok több alapértelmezett betűtípus mappát az Aspose.Wordsben?

 V: Igen, beállíthat több alapértelmezett betűtípus-mappát az Aspose.Words-ben. Csak meg kell adnia az egyéni betűtípus-mappák helyét a segítségével`SetFontsFolders` módszere a`Fonts` osztály.

#### K: Hogyan ellenőrizhetem az Aspose.Wordsben jelenleg beállított alapértelmezett betűtípus-mappákat?

 V: Az Aspose.Wordsben jelenleg definiált alapértelmezett betűtípus-mappák ellenőrzéséhez használhatja a`GetFolders` módszere a`Fonts` osztályba, hogy megkapja a konfigurált font mappák helyét.

#### K: Az alapértelmezett betűtípusmappák beállítása lehetővé teszi egyéni betűtípusok használatát a Word-dokumentumaimban?

V: Igen, az alapértelmezett betűtípusmappák beállításával egyéni betűtípusokat használhat a Word-dokumentumokban. Csak el kell helyeznie a betűtípusokat a megadott mappákba, és az Aspose.Words használni fogja őket a dokumentumok generálásakor vagy manipulálásakor.