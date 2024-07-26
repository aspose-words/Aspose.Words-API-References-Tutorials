---
title: Állítsa be a Fonts mappákat prioritással
linktitle: Állítsa be a Fonts mappákat prioritással
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a betűtípusmappák elsőbbségi beállításához a dokumentum Aspose.Words for .NET használatával történő renderelésekor.
type: docs
weight: 10
url: /hu/net/working-with-fonts/set-fonts-folders-with-priority/
---

Ebben az oktatóanyagban lépésről lépésre végigvezetjük a betűtípusmappák elsőbbségi beállításának folyamatán, amikor egy dokumentumot az Aspose.Words for .NET használatával jelenít meg. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén tudni fogja, hogyan adjon meg több betűtípus-mappát egyéni keresési prioritással, amikor az Aspose.Words for .NET használatával rendereli dokumentumait.

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahová menteni szeretné a szerkesztett renderelt dokumentumot. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Állítsa be a font mappák prioritását
 Ezután beállíthatja a font mappákat prioritásként a segítségével`FontSettings` osztály és a`SetFontsSources()`módszer. Több betűtípust is megadhat a példányok használatával`SystemFontSource`és`FolderFontSource`. Ebben a példában két betűtípus-forrást definiáltunk: az alapértelmezett rendszer-betűtípus-forrást és egy egyéni betűtípus-mappát 1-es prioritással.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## 3. lépés: Töltse be a renderelni kívánt dokumentumot
 Most betöltheti a dokumentumot renderelni a`Document` osztály. Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4. lépés: Mentse el a renderelt dokumentumot
 Végül a renderelt dokumentumot fájlba mentheti a`Save()` módszere a`Document` osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Minta forráskód a Set Fonts Folders With Priority funkcióhoz az Aspose.Words for .NET használatával 
```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan állíthat be prioritást a betűtípusmappák számára, amikor egy dokumentumot az Aspose.Words for .NET használatával renderel. Ennek a lépésről lépésre szóló útmutatónak a követésével könnyedén megadhat több betűtípus-mappát egyéni keresési prioritással a dokumentumok renderelésekor. Az Aspose.Words hatékony és rugalmas API-t kínál a szövegfeldolgozáshoz a dokumentumokban található betűtípusokkal. Ezzel a tudással szabályozhatja és testreszabhatja a dokumentumok renderelésekor használt betűtípusokat az Ön egyedi igényei szerint.

### GYIK

#### K: Hogyan állíthatok be prioritást a font mappáknak az Aspose.Wordsben?

 V: Az Aspose.Words betűtípusmappák prioritásának beállításához használhatja a`SetFontsFoldersWithPriority` módszere a`Fonts` osztályba a font mappák helyeinek és azok fontossági sorrendjének megadásával.

#### K: Mi történik, ha egy betűtípus több különböző prioritású mappában van?

V: Ha egy betűtípus több, eltérő prioritással rendelkező mappában található, az Aspose.Words a legmagasabb prioritású mappa verzióját fogja használni a dokumentumok feldolgozásakor.

#### K: Megadhatok több betűtípus-mappát azonos prioritással az Aspose.Words-ben?

V: Igen, az Aspose.Words-ben több betűtípus-mappát is megadhat azonos prioritással. Az Aspose.Words mindegyiket egyenlő prioritásként veszi figyelembe, amikor betűtípusokat keres a dokumentumokban.

#### K: Hogyan ellenőrizhetem az Aspose.Words-ben prioritást élvező betűtípus-mappákat?

 V: Az Aspose.Words-ben prioritást élvező betűtípus-mappák ellenőrzéséhez használhatja a`GetFolders` módszere a`Fonts` osztályba, hogy megkapja a konfigurált font mappák listáját, beleértve azok prioritási sorrendjét.

#### K: Mi haszna az Aspose.Words fontmappák elsőbbségi beállításának?

V: A betűtípusmappák prioritásának beállítása az Aspose.Words programban lehetővé teszi a betűtípusok keresési sorrendjének szabályozását a Word-dokumentumokban. Ez segít abban, hogy a kívánt betűtípusokat használja, és elkerülje a nem kívánt betűkészlet-helyettesítési problémákat.