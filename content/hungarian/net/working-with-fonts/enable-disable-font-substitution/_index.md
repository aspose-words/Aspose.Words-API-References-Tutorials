---
title: Engedélyezze a Betűtípus-csere letiltását
linktitle: Engedélyezze a Betűtípus-csere letiltását
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan engedélyezheti vagy tilthatja le a betűkészlet-helyettesítést egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fonts/enable-disable-font-substitution/
---
Ebben az oktatóanyagban végigvezetjük, hogyan engedélyezheti vagy tilthatja le a betűkészlet-helyettesítést egy Word-dokumentumban, amikor a .NET Aspose.Words könyvtárával rendereli azt. A betűtípusok helyettesítésének engedélyezése vagy letiltása lehetővé teszi annak szabályozását, hogy a hiányzó betűtípusokat automatikusan alapértelmezett betűtípusra cseréljék-e. Lépésről lépésre segítünk megérteni és megvalósítani a kódot a .NET-projektben.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár
- Egy Word-dokumentum, amelyet betűkészlet-helyettesítéssel vagy anélkül szeretne megjeleníteni

## 1. lépés: Határozza meg a dokumentumkönyvtárat
 Először is be kell állítania a könyvtár elérési útját a Word-dokumentum helyére. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse fel a dokumentumot, és konfigurálja a betűtípus beállításait
 Ezután betöltjük a megjeleníteni kívánt Word-dokumentumot, és létrehozzuk a példányt`FontSettings` osztályt a betűtípus-beállítások kezeléséhez. Az alapértelmezett betűtípus-felülírást a betűtípus nevének megadásával állítjuk be`DefaultFontName` és tiltsa le a betűtípus-információk felülbírálását`Enabled` állítva`false`.

```csharp
// Töltse be a dokumentumot
Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurálja a betűtípus beállításait
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Alkalmazza a betűtípus-beállításokat a dokumentumra
doc.FontSettings = fontSettings;
```

## 3. lépés: Mentse el a renderelt dokumentumot
Végül elmentjük a renderelt dokumentumot, amely tiszteletben tartja a megadott betűtípus-felülírási beállításokat.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Minta forráskód a Betűtípus-helyettesítés letiltásának engedélyezése az Aspose.Words for .NET használatával funkcióhoz 

```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Következtetés
Ebben az oktatóanyagban azt láthattuk, hogyan lehet engedélyezni vagy letiltani a betűkészlet-helyettesítést egy Word-dokumentumban, amikor az Aspose.Words for .NET segítségével történik. A betűtípusok helyettesítésének szabályozásával befolyásolhatja, hogy a hiányzó betűtípusok hogyan legyenek kezelve a megjelenített dokumentumokban. Ne habozzon használni ezt a funkciót a Word-dokumentumok betűtípus-kezelésének testreszabásához.

### GYIK

#### K: Hogyan engedélyezhetem a betűtípusok helyettesítését egy Word-dokumentumban az Aspose.Words segítségével?

V: A Word-dokumentumban az Aspose.Words segítségével történő betűkészlet-helyettesítés engedélyezéséhez az API segítségével megadhatja a helyettesítő betűtípusokat, amelyeket akkor használ, ha a szükséges betűtípusok nem állnak rendelkezésre. Ez biztosítja a következetes szövegvizualizációt, még az eredeti betűtípusok nélkül is.

#### K: Lehetséges-e letiltani a betűkészlet-helyettesítést egy Word-dokumentumban az Aspose.Words használatával?

V: Igen, az Aspose.Words segítségével letilthatja a betűkészlet helyettesítését egy Word-dokumentumban. Az API használatával megakadályozhatja, hogy a Word a szükséges betűtípusokat más betűtípusokkal helyettesítse, ami megőrzi a szöveg eredeti megjelenését.

#### K: Mi történik, ha a szükséges betűtípusok hiányoznak a Word-dokumentum pótlása során?

V: Ha egy Word-dokumentumban hiányoznak a szükséges betűtípusok a helyettesítés során, az Aspose.Words képes észlelni ezt a problémát, és lehetőségeket kínál a javításra. Dönthet úgy, hogy a hiányzó betűtípusokat helyettesíti más betűtípusokkal, vagy beillesztheti a hiányzó betűtípusokat a dokumentumba, így biztosítva a megfelelő megjelenítést.

#### K: Hogyan kezelhetem a hiányzó betűtípusokat, amikor a Word-dokumentumban az Aspose.Words-szel helyettesítem?

V: A hiányzó betűtípusok kezeléséhez, amikor egy Word-dokumentumban Aspose.Words-szel helyettesíti, használhatja az API-t a hiányzó betűtípusok észlelésére és a felbontási beállítások megadására. Igényeitől függően választhatja a hiányzó betűtípusok helyettesítését alternatív betűtípusokkal, vagy beillesztheti a hiányzó betűtípusokat a dokumentumba.

#### K: Fontos a betűkészlet-helyettesítés szabályozása egy Word-dokumentumban?

V: Igen, a szöveg vizuális integritásának megőrzése érdekében fontos a betűkészlet-helyettesítés szabályozása a Word-dokumentumban. Az Aspose.Words használatával engedélyezheti vagy letilthatja a betűtípusok helyettesítését, biztosíthatja a szükséges betűtípusok használatát, és elkerülheti a hiányzó vagy helyettesített betűtípusokkal kapcsolatos problémákat.