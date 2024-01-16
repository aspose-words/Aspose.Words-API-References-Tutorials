---
title: Formátum 1Bpp Indexelt
linktitle: Formátum 1Bpp Indexelt
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan formázhat képeket 1 bpp-ben az Aspose.Words for .NET segítségével indexelve. Teljes oktatóanyag az alacsony színmélységű képekhez.
type: docs
weight: 10
url: /hu/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Ebben az oktatóanyagban megvizsgáljuk az Aspose.Words for .NET "Format 1Bpp Indexed" funkciójához biztosított C# forráskódot. Ez a funkció lehetővé teszi, hogy a dokumentumokban lévő képeket PNG formátumban formázza 1 bit/pixel (1 bpp) színmélységgel és indexelt színmóddal.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy beállította fejlesztői környezetét az Aspose.Words for .NET segítségével. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat, és importálta a megfelelő névtereket.

## 2. lépés: A dokumentum betöltése

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Ebben a lépésben a dokumentumot a`Document` metódust, és átadja a betöltendő DOCX fájl elérési útját.

## 3. lépés: Konfigurálja a kép biztonsági mentési beállításait

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Ebben a lépésben konfiguráljuk a képek biztonsági mentési beállításait. Létrehozunk egy újat`ImageSaveOptions`objektum megadja a kívánt mentési formátumot, itt "Png" a PNG formátumhoz. Meghatározzuk továbbá a képbe belefoglalandó oldalt, a fekete-fehér színmódot és az indexelt 1 bpp pixelformátumot.

## 4. lépés: Képek biztonsági mentése

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Ebben az utolsó lépésben a dokumentum képeit PNG formátumban mentjük a`Save` metódust, és átadja a kimeneti fájl elérési útját a megadott mentési beállításokkal együtt.

Most már futtathatja a forráskódot a dokumentumképek PNG formátumban való formázásához, 1 bpp indexelt színmélységgel. Az eredményül kapott fájl a megadott könyvtárba kerül mentésre "WorkingWithImageSaveOptions.Format1BppIndexed.Png" néven.

### Minta forráskód az 1Bpp formátumhoz, indexelve az Aspose.Words for .NET használatával

```csharp 
 
			 // A dokumentumkönyvtár elérési útja
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Következtetés

Ebben az oktatóanyagban megvizsgáltuk az 1Bpp indexelt formátum funkciót az Aspose.Words for .NET segítségével. Megtanultuk, hogyan formázhatunk képeket egy dokumentumban PNG formátumban 1 bit/pixel (1 bpp) színmélységgel és indexelt színmóddal.

Ez a funkció akkor hasznos, ha alacsony színmélységgel és kis fájlmérettel szeretne képeket készíteni. Az 1Bpp indexelt formátum lehetővé teszi a képek indexelt színpaletta használatával történő megjelenítését, ami bizonyos alkalmazásoknál előnyös lehet.

Az Aspose.Words for .NET fejlett funkciók széles skáláját kínálja a dokumentumok kezeléséhez és létrehozásához. Az 1Bpp indexelt formátum egyike a sok hatékony eszköznek, amelyet az Ön rendelkezésére bocsát.