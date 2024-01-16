---
title: Betűtípusbeállítások Alapértelmezett példány
linktitle: Betűtípusbeállítások Alapértelmezett példány
second_title: Aspose.Words Document Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan konfigurálhatja az alapértelmezett betűkészlet-beállításokat egy Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fonts/font-settings-default-instance/
---

Ebben az oktatóanyagban végigvezetjük, hogyan konfigurálhatja az alapértelmezett betűtípus-beállításokat egy Word-dokumentumban az Aspose.Words könyvtár segítségével a .NET-hez. Az alapértelmezett betűkészlet-beállítások lehetővé teszik a dokumentumok betöltésekor és renderelésekor használt betűkészlet-források megadását. Lépésről lépésre segítünk megérteni és megvalósítani a kódot a .NET-projektben.

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

## 2. lépés: Konfigurálja az alapértelmezett betűtípus-beállításokat
 Ezután létrehozunk egy példányt`FontSettings` segítségével`FontSettings.DefaultInstance`, majd megadjuk a dokumentumok betöltésekor és megjelenítésekor használt betűtípus-forrásokat. Ebben a példában egy rendszer- és egy mappa betűtípus-forrást használunk.

```csharp
// Konfigurálja az alapértelmezett betűtípus-beállításokat
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 3. lépés: Töltse fel a dokumentumot a betűtípus-beállításokkal
 Most betöltjük a dokumentumot a segítségével`LoadOptions` és megadja a használni kívánt betűtípus-beállításokat.

```csharp
// Töltse be a dokumentumot a betűtípus-beállításokkal
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Minta forráskód a fontbeállítások alapértelmezett példányához az Aspose.Words for .NET használatával 
```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Következtetés
Ebben az oktatóanyagban láthattuk, hogyan konfigurálhatja az alapértelmezett betűkészlet-beállításokat egy Word-dokumentumban az Aspose.Words for .NET segítségével. A dokumentumok betöltésekor és renderelésekor használt betűkészlet-források megadásával szabályozhatja a betűtípusok megjelenését a dokumentumokban. Nyugodtan használhatja ezt a funkciót projektjei betűtípus-beállításainak testreszabásához.

### GYIK

#### K: Hogyan állíthatom be az Aspose.Words alapértelmezett betűtípusát?

 V: Az Aspose.Words alapértelmezett betűtípusának beállításához használhatja a`FontSettings` osztály és a`DefaultFontName` tulajdonság, amely megadja a kívánt betűtípus nevét.

#### K: Megadhatom az alapértelmezett betűméretet az Aspose.Wordsben?

 V: Igen, megadhatja az alapértelmezett betűméretet az Aspose.Words-ben a`DefaultFontSize` tulajdona a`FontSettings` osztály. Beállíthatja a kívánt pontméretet.

#### K: Beállítható az alapértelmezett betűszín az Aspose.Wordsben?

 V: Igen, beállíthatja az alapértelmezett betűszínt az Aspose.Words-ben a`DefaultColor` tulajdona a`FontSettings` osztály. A színt RGB értékek vagy előre meghatározott nevek segítségével adhatja meg.

#### K: Az alapértelmezett betűkészlet-beállítások minden dokumentumra érvényesek?

V: Igen, az alapértelmezett betűtípus-beállítások az Aspose.Words programban létrehozott vagy szerkesztett összes dokumentumra vonatkoznak, kivéve, ha egy adott dokumentumhoz speciális beállítások vannak megadva.