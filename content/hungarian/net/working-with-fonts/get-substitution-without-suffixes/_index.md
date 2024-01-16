---
title: Helyettesítés utótagok nélkül
linktitle: Helyettesítés utótagok nélkül
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan kaphat utótag nélküli felülírásokat Word-dokumentumokban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fonts/get-substitution-without-suffixes/
---

Ebben az oktatóanyagban bemutatjuk, hogyan szerezheti be az utótagok nélküli felülírásokat egy Word-dokumentumban az Aspose.Words könyvtár segítségével a .NET-hez. Az utótagok nélküli helyettesítések a betűkészlet-helyettesítési problémák megoldására szolgálnak dokumentumok megjelenítése vagy nyomtatása során. Lépésről lépésre segítünk megérteni és megvalósítani a kódot a .NET-projektben.

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

## 2. lépés: Töltse be a dokumentumot, és konfigurálja a helyettesítéseket utótagok nélkül
 Ezután betöltjük a dokumentumot a`Document` osztályt, és konfigurálja az utótag nélküli helyettesítéseket a`DocumentSubstitutionWarnings` osztály. A betűtípusokat tartalmazó mappa megadásával fontforrást is hozzáadunk.

```csharp
// Töltse be a dokumentumot, és konfigurálja a helyettesítéseket utótagok nélkül
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## 3. lépés: Mentse el a dokumentumot
Végül elmentjük a dokumentumot az utótag nélküli felülírásokkal.

```csharp
// Mentse el a dokumentumot
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Minta forráskód az Aspose.Words for .NET használatával végzett helyettesítés nélkül utótagok nélkül 
```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Következtetés
Ebben az oktatóanyagban azt láthattuk, hogyan lehet utótagok nélküli felülírásokat elérni egy Word-dokumentumban az Aspose.Words for .NET segítségével. Az utótagok nélküli helyettesítések hasznosak a betűtípus-helyettesítési problémák megoldásában. Nyugodtan használja ezt a funkciót a dokumentumok megjelenítésének és nyomtatásának javítására.

### GYIK

#### K: Miért ad az Aspose.Words utótagokat a betűtípusok helyettesítéséhez?

V: Az Aspose.Words utótagokat ad a betűtípusok helyettesítéséhez, hogy elkerülje az eredeti és helyettesített betűtípusok közötti ütközéseket. Ez segít maximális kompatibilitást biztosítani a dokumentumok konvertálása és kezelése során.

#### K: Hogyan kérhetem le a betűkészlet-helyettesítéseket utótagok nélkül az Aspose.Words-ben?

 V: Az Aspose.Words utótagok nélküli betűkészlet-helyettesítéseinek lekéréséhez használhatja a`FontSubstitutionSettings` osztály és a`RemoveSuffixes` ingatlan. Ennek a tulajdonságnak a beállítása`true` megkapja a betűtípus-helyettesítéseket a hozzáadott utótagok nélkül.

#### K: Lehetséges letiltani az utótagok hozzáadását a betűtípusok helyettesítéséhez az Aspose.Words programban?

V: Nem, nem lehet letiltani az utótagok hozzáadását a betűtípusok helyettesítéséhez az Aspose.Words programban. Az utótagok alapértelmezés szerint a dokumentumok kompatibilitásának és konzisztenciájának biztosítására szolgálnak.

#### K: Hogyan szűrhetem ki a nem kívánt utótagokat az Aspose.Words betűtípus-helyettesítéseiben?

 V: Az Aspose.Words betűtípus-helyettesítéseiben előforduló nem kívánt utótagok kiszűréséhez karakterlánc-feldolgozási technikákat használhat, például`Replace` vagy`Substring` módszerek a nem kívánt utótagok eltávolítására.