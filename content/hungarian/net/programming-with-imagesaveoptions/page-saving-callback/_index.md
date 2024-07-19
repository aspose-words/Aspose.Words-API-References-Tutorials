---
title: Oldal mentése Visszahívás
linktitle: Oldal mentése Visszahívás
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan testreszabhatja a dokumentumoldalak képekké történő mentését az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-imagesaveoptions/page-saving-callback/
---

Ebben az oktatóanyagban megvizsgáljuk az oldalmentési visszahíváshoz biztosított C# forráskódot az Aspose.Words képmentési lehetőségeivel a .NET-hez. Ez a funkció lehetővé teszi egyéni műveletek végrehajtását, amikor a dokumentum minden oldalát képként menti.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Ebben a lépésben egy új létrehozásával konfiguráljuk a képmentési beállításokat`ImageSaveOptions` tárgy. Megadjuk a kívánt biztonsági mentési formátumot, itt a "Png" a PNG formátum. Használjuk`PageSet` a mentendő oldalak tartományának megadásához, itt a dokumentum első oldalától az utolsó oldalig (`doc.PageCount - 1`). Be is állítjuk`PageSavingCallback` egy példányára`HandlePageSavingCallback`, amely egy egyéni osztály az oldalmentő visszahívás kezelésére.

## 4. lépés: Az Oldal mentése visszahívás végrehajtása

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Itt hajtsa végre egyéni műveleteit
         // Az oldaladatokat az "args.PageIndex" tulajdonságon keresztül érheti el
         // Az egyes oldalak mentési beállításait külön-külön is módosíthatja
     }
}
```

 Ebben a lépésben megvalósítjuk a`HandlePageSavingCallback` osztály, amely megvalósítja a`IPageSavingCallback` felület. Testreszabhatja ezt az osztályt, ha hozzáadja a konkrét műveleteket a`PageSaving` módszer. Az oldal információit a következőn keresztül érheti el`args.PageIndex` tulajdona a`PageSavingArgs` Az objektum argumentumként került átadásra.

## 5. lépés: Oldalak mentése képként

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Ebben az utolsó lépésben a dokumentum minden oldalát képként mentjük a segítségével`Save` metódust, és átadja a kimeneti fájl elérési útját a`.png` kiterjesztést, a megadott mentési beállításokkal együtt.

Most már futtathatja a forráskódot egyéni műveletek végrehajtásához, amikor a dokumentum minden oldalát képként menti. Az eredményül kapott fájl a megadott könyvtárba kerül mentésre "WorkingWithImageSaveOptions.PageSavingCallback.png" néven.

### Minta forráskód az oldalmentési visszahíváshoz az Aspose.Words for .NET használatával


```csharp 
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk az oldalmentési visszahívási funkciót az Aspose.Words képmentési lehetőségeivel a .NET-hez. Megtanultuk, hogyan kell egyéni műveleteket végrehajtani a dokumentum minden oldalának képként történő mentésekor.

Ez a funkció akkor hasznos, ha bizonyos műveleteket szeretne végrehajtani az egyes oldalakon, amikor képekké konvertál. Hozzáférhet az oldal információihoz, és testreszabhatja a biztonsági mentési beállításokat, vagy más oldalspecifikus feldolgozást hajthat végre.

Az Aspose.Words for .NET fejlett funkciók széles skáláját kínálja a dokumentumok kezeléséhez és létrehozásához. Az Oldal mentése Emlékeztető egyike a sok hatékony eszköznek, amellyel testreszabhatja az oldalak képekké történő mentésének folyamatát.