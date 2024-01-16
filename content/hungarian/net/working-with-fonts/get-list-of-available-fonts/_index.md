---
title: Szerezze meg az elérhető betűtípusok listáját
linktitle: Szerezze meg az elérhető betűtípusok listáját
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan szerezheti be az Aspose.Words for .NET-ben elérhető betűtípusok listáját.
type: docs
weight: 10
url: /hu/net/working-with-fonts/get-list-of-available-fonts/
---
Ebben az oktatóanyagban elmagyarázzuk, hogyan szerezheti be az Aspose.Words for .NET-ben elérhető betűtípusok listáját. Az elérhető betűtípusok listája megmutatja, hogy mely betűtípusokat használhatja a dokumentumokban. Lépésről lépésre segítünk megérteni és megvalósítani a kódot a .NET-projektben.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár

## 1. lépés: Határozza meg a dokumentumkönyvtárat
 Először is be kell állítania a könyvtár elérési útját a Word-dokumentum helyére. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Konfigurálja a betűtípusforrásokat
 Ezután létrehozunk egy példányt`FontSettings` és szerezze be a meglévő fontforrásokat a`GetFontsSources()` módszer. A betűtípusokat tartalmazó mappa megadásával egy új fontforrást is hozzáadunk.

```csharp
// Betűtípus-források konfigurálása
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Új betűtípus-forrás hozzáadása
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## 3. lépés: Szerezze meg az elérhető betűtípusok listáját
 Most a rendelkezésre álló betűtípusok között fogunk böngészni a`GetAvailableFonts()` módszert az első frissített betűtípus-forráson.

```csharp
// Szerezze meg az elérhető betűtípusok listáját
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Minta forráskód az elérhető betűtípusok listájának lekéréséhez az Aspose.Words for .NET használatával 

```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Adjon hozzá egy új mappaforrást, amely utasítja az Aspose.Words-t, hogy keressen betűtípusokat a következő mappában.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Adja hozzá a fontjainkat tartalmazó egyéni mappát a meglévő fontforrások listájához.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Következtetés
Ebben az oktatóanyagban megnéztük, hogyan szerezheti be az Aspose.Words for .NET-ben elérhető betűtípusok listáját. Ezzel megtudhatja, milyen betűtípusokat használhat a dokumentumokban. Nyugodtan használja ezt a funkciót az igényeinek megfelelő betűtípus kiválasztásához.

### GYIK

#### K: Hogyan kérhetem le az Aspose.Words-ben elérhető betűtípusok listáját?

 V: Az Aspose.Words-ben elérhető betűtípusok listájának lekéréséhez használja a`FontsProvider` osztály és a`GetAvailableFonts` módszer. Ez a módszer visszaadja a rendszerre telepített összes betűtípus listáját.

#### K: Szűrhetem a rendelkezésre álló betűtípusok listáját bizonyos kritériumok szerint az Aspose.Wordsben?

V: Igen, szűrheti az Aspose.Words-ben elérhető betűtípusok listáját meghatározott kritériumok alapján. Például szűrheti a betűtípusokat család, stílus vagy nyelv szerint.

#### K: Hogyan használhatom a Word dokumentumaimban elérhető betűtípusok listáját?

 V: A Word dokumentumokban elérhető betűtípusok listájának használatához böngészhet a listában, és kiválaszthatja a megfelelő betűtípusokat a`FontSettings` osztályban Aspose.Words.