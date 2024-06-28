---
title: Set Fonts Folders System és egyéni mappa
linktitle: Set Fonts Folders System és egyéni mappa
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a rendszer- és az egyéni betűtípus-mappák beállításához, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel.
type: docs
weight: 10
url: /hu/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a rendszer-betűtípus-mappák és az egyéni mappa beállításának folyamatán, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Ennek az oktatóanyagnak a végére tudni fogja, hogyan adhat meg több betűtípus-mappát, beleértve a rendszermappát és egy egyéni mappát is, amelyeket a dokumentumok Aspose.Words for .NET használatával történő renderelésekor használ.

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

## 3. lépés: Állítsa be a rendszer- és az egyéni betűtípus-mappákat
 Most beállíthatja a rendszer betűtípus-mappáit és egy egyéni mappát a segítségével`FontSettings` osztály és a`SetFontsSources()` módszer. Először is le kell kérnie a környezetfüggő fontforrások listáját a használatával`GetFontsSources()` és tárolja egy listában. Ezután létrehozhat egy új példányt`FolderFontSource` megadja a betűtípusokat tartalmazó egyéni mappa elérési útját. Adja hozzá ezt a példányt a meglévő fontforrások listájához. Végül használd`SetFontsSources()` hogy frissítse a fontforrásokat az új listával.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 4. lépés: Alkalmazza a betűtípusbeállításokat
 Ezután alkalmaznia kell a betűtípus-beállításokat a dokumentumban a`FontSettings` tulajdona a`Document` osztály.

```csharp
doc.FontSettings = fontSettings;
```

## 5. lépés: Mentse el a renderelt dokumentumot
Végül a renderelt dokumentumot fájlba mentheti a következővel

   használni a`Save()` módszere a`Document` osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Minta forráskód a Set Fonts Folders rendszerhez és az egyéni mappákhoz az Aspose.Words for .NET használatával 

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Az alapértelmezés szerint keresett környezetfüggő betűtípus-források tömbjének lekérése.
// Például ez egy "Windows\Fonts\" forrást tartalmaz egy Windows gépen.
// Ezt a tömböt hozzáadjuk egy új listához, hogy sokkal könnyebbé tegyük a betűtípus-bejegyzések hozzáadását vagy eltávolítását.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Adjon hozzá egy új mappaforrást, amely utasítja az Aspose.Words-t, hogy keressen betűtípusokat a következő mappában.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Adja hozzá a fontjainkat tartalmazó egyéni mappát a meglévő fontforrások listájához.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthat be rendszerbetűtípus-mappákat és egyéni mappákat, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel. A lépésenkénti útmutató követésével egyszerűen megadhat több betűtípus-mappát, beleértve a rendszermappát és egy egyéni mappát is, amelyeket a dokumentumok renderelésekor használ. Az Aspose.Words hatékony és rugalmas API-t kínál a szövegfeldolgozáshoz a dokumentumokban található betűtípusokkal. Ezzel a tudással szabályozhatja és testreszabhatja a dokumentumok renderelésekor használt betűtípusokat az Ön egyedi igényei szerint.

### GYIK

#### K: Hogyan állíthatok be rendszerbetűtípus-mappákat az Aspose.Words-ben?

V: A rendszer font mappáinak beállításához az Aspose.Wordsben semmit sem kell tennie. Az Aspose.Words automatikusan az operációs rendszerre telepített rendszer-betűtípusokat használja.

#### K: Hogyan állíthatok be egyéni betűtípus-mappákat az Aspose.Words-ben?

 V: Az Aspose.Words egyéni betűtípus-mappáinak beállításához használhatja a`SetFontsFolders` módszere a`Fonts` osztály, amely megadja az egyéni betűtípus-mappák helyét.

#### K: Megadhatok több egyéni betűtípus-mappát az Aspose.Words-ben?

 V: Igen, több egyéni betűtípus-mappát is megadhat az Aspose.Words-ben a segítségével`SetFontsFolders` módszere a`Fonts` osztályt a mappahelyek listájával.

#### K: Hogyan ellenőrizhetem az Aspose.Words-ben meghatározott betűtípus-mappákat?

 Az Aspose.Words-ben meghatározott betűtípus-mappák ellenőrzéséhez használhatja a`GetFolders` módszere a`Fonts` osztályba, hogy megkapja a konfigurált betűtípus mappák listáját.

#### K: Az egyéni mappák betűtípusai elsőbbséget élveznek az Aspose.Words rendszer betűtípusaival szemben?

V: Igen, az egyéni mappák betűtípusai elsőbbséget élveznek az Aspose.Words rendszer betűtípusaival szemben. Ha egy betűtípus az egyéni mappákban és a rendszer-betűtípusokban is megtalálható, az Aspose.Words az egyéni mappából származó verziót fogja használni.