---
title: Frissítse az utolsó megtakarított idő tulajdonságot
linktitle: Frissítse az utolsó megtakarított idő tulajdonságot
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan frissítheti automatikusan az Utolsó megtakarított idő tulajdonságot a dokumentum Aspose.Words for .NET segítségével történő mentésekor.
type: docs
weight: 10
url: /hu/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
Ebben az oktatóanyagban megvizsgáljuk a biztosított C# forráskódot, hogy frissítsük az utolsó mentési idő tulajdonságot, amikor egy dokumentumot Aspose.Words for .NET használatával mentünk. Ez a funkció lehetővé teszi a generált dokumentum utolsó mentési idő tulajdonságának automatikus frissítését.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy beállította fejlesztői környezetét az Aspose.Words for .NET segítségével. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat, és importálta a megfelelő névtereket.

## 2. lépés: A dokumentum betöltése

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Ebben a lépésben a dokumentumot a`Document` metódust, és átadja a betöltendő DOCX fájl elérési útját.

## 3. lépés: Az OOXML biztonsági mentési beállításainak konfigurálása

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 Ebben a lépésben konfiguráljuk az OOXML mentési beállításokat a`OoxmlSaveOptions` osztály. Beállítással engedélyezzük az utolsó mentési idő tulajdonság automatikus frissítését`UpdateLastSavedTimeProperty` nak nek`true`.

## 4. lépés: Mentse el a dokumentumot frissített tulajdonsággal

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Az utolsó lépésben a dokumentumot a`Save` metódust, és átadja a kimeneti fájl elérési útját a`.docx` kiterjesztést, a megadott mentési beállításokkal együtt.

Most már futtathatja a forráskódot, hogy automatikusan frissítse az utolsó mentési idő tulajdonságot egy dokumentum mentésekor. Az eredményül kapott fájl a megadott könyvtárba kerül mentésre "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx" néven.

### Minta forráskód a Last Saved Time tulajdonság frissítéséhez az Aspose.Words for .NET használatával 

```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a legutóbbi mentési idő tulajdonság automatikus frissítésének funkcióját, amikor egy dokumentumot az Aspose.Words for .NET használatával ment. Ha engedélyezi ezt a funkciót az OOXML mentési beállításokkal, akkor biztosíthatja, hogy az utolsó mentési idő tulajdonság automatikusan frissüljön a generált dokumentumban.

Az utolsó mentési idő tulajdonság frissítése hasznos lehet egy dokumentum változásainak és verzióinak nyomon követéséhez. Azt is nyomon követi, hogy a dokumentumot mikor mentették utoljára, ami különféle helyzetekben hasznos lehet.

Az Aspose.Words for .NET megkönnyíti a Last Backup Time tulajdonság automatikus frissítését rugalmas és hatékony biztonsági mentési lehetőségek biztosításával. Ezt a funkciót integrálhatja projektjeibe, így biztosítva, hogy a generált dokumentumok pontos biztonsági mentési információkkal rendelkezzenek.