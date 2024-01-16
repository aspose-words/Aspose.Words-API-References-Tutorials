---
title: Szerezze be a Tiff Page Range szolgáltatást
linktitle: Szerezze be a Tiff Page Range szolgáltatást
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan bonthat ki egy sor TIFF-oldalt az Aspose.Words for .NET segítségével. Teljes oktatóanyag az egyéni TIFF-fájlokhoz.
type: docs
weight: 10
url: /hu/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

Ebben az oktatóanyagban megvizsgáljuk a mellékelt C# forráskódot, hogy egy sor TIFF-oldalt kapjunk az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi az oldalak meghatározott tartományának kinyerését a dokumentumból, és TIFF-fájlként történő elmentését.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy beállította fejlesztői környezetét az Aspose.Words for .NET segítségével. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat, és importálta a megfelelő névtereket.

## 2. lépés: A dokumentum betöltése

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Ebben a lépésben a dokumentumot a`Document` metódust, és átadja a betöltendő DOCX fájl elérési útját.

## 3. lépés: Mentse el a teljes dokumentumot TIFF formátumban

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

Ebben a lépésben a teljes dokumentumot TIFF formátumban mentjük a`Save` metódust, és megadja a kimeneti fájl elérési útját a kiterjesztéssel`.tiff`.

## 4. lépés: Állítsa be az oldaltartomány biztonsági mentési beállításait

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Ebben a lépésben biztonsági mentési beállításokat konfigurálunk az adott oldaltartományhoz. Létrehozunk egy újat`ImageSaveOptions` objektum megadja a kívánt mentési formátumot, itt "Tiff" a TIFF formátumhoz. Használjuk`PageSet` a kivonatolni kívánt oldalak tartományának megadásához itt a 0. oldaltól az 1. oldalig (beleértve). Beállítottuk a TIFF tömörítést is`Ccitt4` és a felbontás 160 dpi.

## 5. lépés: Az oldaltartomány mentése TIFF formátumba

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Ebben az utolsó lépésben elmentjük a megadott oldaltartományt TIFF formátumban a`Save` metódussal, és átadja a kimeneti fájl elérési útját`.tiff` kiterjesztés, valamint a megadott mentési beállítások .

Most már futtathatja a forráskódot, hogy egy adott oldaltartományt nyerjen ki a dokumentumból, és mentse azokat TIFF-fájlként. Az eredményül kapott fájlokat a rendszer a megadott könyvtárba menti „WorkingWithImageSaveOptions.MultipageTiff.tiff” néven a teljes dokumentumhoz, és „WorkingWithImageSaveOptions.GetTiffPageRange.tiff” néven a megadott oldaltartományhoz.

### A Get Tiff Page Range mintaforráskódja az Aspose.Words for .NET használatával

```csharp 

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a TIFF-oldalak széles választékának beszerzését az Aspose.Words for .NET segítségével. Megtanultuk, hogyan lehet kivonni egy bizonyos oldaltartományt egy dokumentumból, és elmenteni TIFF-fájlként.

Ez a funkció akkor hasznos, ha csak bizonyos oldalakat szeretne kivonni egy dokumentumból, és szabványos képformátumban, például TIFF-ben szeretné menteni. A legjobb minőségű TIFF-fájlok elérése érdekében testreszabhatja a tömörítési és felbontási beállításokat is.

Az Aspose.Words for .NET fejlett funkciók széles skáláját kínálja a dokumentumok kezeléséhez és létrehozásához. A TIFF oldaltartomány beszerzése egyike a sok hatékony eszköznek, amelyet az Ön rendelkezésére bocsát.

Nyugodtan integrálhatja ezt a funkciót az Aspose.Words for .NET projektjébe, hogy meghatározott oldaltartományokat kinyerhessen és menthessen TIFF formátumban dokumentumaiból.