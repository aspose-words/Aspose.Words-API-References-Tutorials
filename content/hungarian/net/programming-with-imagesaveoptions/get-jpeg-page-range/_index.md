---
title: Szerezze be a Jpeg oldaltartományt
linktitle: Szerezze be a Jpeg oldaltartományt
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szerezhet be egy sor JPEG oldalt az Aspose.Words for .NET segítségével. Teljes oktatóanyag az egyéni képek kinyeréséhez.
type: docs
weight: 10
url: /hu/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Ebben az oktatóanyagban az Aspose.Words for .NET-hez tartozó "JPEG-oldalak tartományának lekérése" funkcióhoz biztosított C#-forráskódot fogjuk felfedezni. Ez a funkció lehetővé teszi a dokumentum bizonyos oldalainak JPEG formátumú képekké alakítását.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Ebben a lépésben konfiguráljuk a képek biztonsági mentési beállításait. Létrehozunk egy újat`ImageSaveOptions` objektum, amely megadja a kívánt mentési formátumot, itt a "Jpeg" a JPEG formátum. A konvertálandó oldalak körét is beállítjuk a`PageSet`tárgy. Végül beállítjuk a kép fényerejét és kontrasztját a segítségével`ImageBrightness`és`ImageContrast` tulajdonságait, ill. A vízszintes felbontást is megváltoztatjuk a`HorizontalResolution` ingatlan.

## 4. lépés: Képek biztonsági mentése

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Ebben az utolsó lépésben elmentjük a megadott oldaltartomány képeit JPEG formátumban a`Save` metódust, és átadja a kimeneti fájl elérési útját a megadott mentési beállításokkal együtt.

Most már futtathatja a forráskódot, hogy a dokumentum bizonyos oldalait JPEG képekké alakítsa. Az eredményül kapott fájl a megadott könyvtárba kerül mentésre "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg" néven.

### Minta forráskód a Get Jpeg Page Range fájlhoz az Aspose.Words For .NET használatával

```csharp 
 // A dokumentumkönyvtár elérési útja
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Állítsa a „PageSet” értéket „0” értékre, hogy csak a dokumentum első oldalát konvertálja.
options.PageSet = new PageSet(0);

// Módosítsa a kép fényerejét és kontrasztját.
// Mindkettő 0-1 skálán van, és alapértelmezés szerint 0,5.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Módosítsa a vízszintes felbontást.
// Ezeknek a tulajdonságoknak az alapértelmezett értéke 96,0, 96 dpi felbontás esetén.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a JPEG oldaltartomány létrehozásának funkcionalitását az Aspose.Words for .NET segítségével. Megtanultuk, hogyan alakíthatunk át egy dokumentum adott oldaltartományát JPEG formátumú képekké, miközben személyre szabjuk a mentési beállításokat.

Ez a funkció akkor hasznos, ha bizonyos oldalakat szeretne kinyerni egy dokumentumból, és JPEG-képként menteni. Beállíthatja a képek fényerejét, kontrasztját és vízszintes felbontását is, hogy személyre szabott eredményeket érjen el.

Az Aspose.Words for .NET fejlett funkciók széles skáláját kínálja a dokumentumok kezeléséhez és létrehozásához. A JPEG oldaltartomány beszerzése egyike a sok hatékony eszköznek, amelyet az Ön rendelkezésére bocsát.

Nyugodtan integrálhatja ezt a funkciót az Aspose.Words for .NET projektjébe, hogy kiváló minőségű JPEG képeket nyerjen ki dokumentumaiból.