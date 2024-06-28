---
title: Állítsa be a Fonts mappát
linktitle: Állítsa be a Fonts mappát
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be a betűtípus-könyvtárat az Aspose.Words for .NET-ben, és hogyan biztosíthatja a dokumentumokban használt betűtípusok elérhetőségét.
type: docs
weight: 10
url: /hu/net/working-with-fonts/set-fonts-folder/
---
Ebben az oktatóanyagban bemutatjuk, hogyan állíthatja be a fonts könyvtárat az Aspose.Words for .NET-ben. Megtanulja, hogyan adhatja meg a Word-dokumentumban használt betűtípusokat tartalmazó könyvtárat.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először állítsa be a könyvtár elérési útját a Word-dokumentum helyére. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Állítsa be a betűtípus-könyvtárat
 Hozzon létre egy példányt a`FontSettings` osztályt, és használja a`SetFontsFolder` metódussal adja meg a betűtípusokat tartalmazó könyvtárat. Cserélje ki`"Fonts"` a tényleges fonts könyvtár nevével.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## 3. lépés: Töltse be a dokumentumot a betűtípus-beállításokkal
 Használja a`LoadOptions` osztályban a betűtípus-beállítások megadásához`FontSettings` választási lehetőség. Ezután használja a`Document` osztályt a dokumentum betöltéséhez ezekkel a beállításokkal.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Minta forráskód a Set Fonts mappához az Aspose.Words for .NET használatával 

```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Következtetés
Gratulálok ! Most már tudja, hogyan kell beállítani a fonts könyvtárat az Aspose.Words for .NET-ben. Ezzel a funkcióval biztosíthatja a dokumentumban használt betűtípusok elérhetőségét, valamint a betűtípusok megjelenítésének következetességét.

### GYIK

#### K: Hogyan állíthatok be egyéni betűtípus-mappát az Aspose.Words-ben?

 V: Egyéni betűtípusmappa beállításához az Aspose.Words alkalmazásban használhatja a`FontsFolder` osztály és a`SetFontsFolders` metódus, amely megadja a betűtípusokat tartalmazó mappa elérési útját.

#### K: Beállíthatok több betűtípus mappát az Aspose.Wordsben?

 V: Igen, több betűtípus-mappát is beállíthat az Aspose.Words-ben a következő meghívásával`SetFontsFolders` metódust többször is a használni kívánt különböző betűtípusmappák elérési útjával.

#### K: Mi történik, ha a dokumentumban használt betűtípus nem található a megadott betűtípus mappákban?

V: Ha a dokumentumban használt betűtípus nem található az Aspose.Words-ben meghatározott betűtípus-mappákban, akkor a rendszer egy helyettesítő betűtípust használ helyette. Ez biztosítja, hogy a dokumentum szövege mindig helyesen jelenjen meg, még akkor is, ha az eredeti betűtípus nem elérhető.

#### K: Az Aspose.Words-ben meghatározott betűtípus-mappák elsőbbséget élveznek a rendszerre telepített betűtípusokkal szemben?

V: Igen, az Aspose.Words-ben meghatározott betűkészlet-mappák elsőbbséget élveznek a rendszerre telepített betűtípusokkal szemben. Ez azt jelenti, hogy ha egy azonos nevű betűtípus megtalálható mind a definiált betűtípusmappákban, mind a rendszer betűtípusaiban, akkor a Word-dokumentumok feldolgozása során a fontmappában lévő verzió kerül felhasználásra.