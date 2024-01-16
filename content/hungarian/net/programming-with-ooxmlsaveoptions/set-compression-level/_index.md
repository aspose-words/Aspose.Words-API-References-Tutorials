---
title: Állítsa be a tömörítési szintet
linktitle: Állítsa be a tömörítési szintet
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be a tömörítési szintet egy dokumentum Aspose.Words for .NET segítségével történő mentésekor.
type: docs
weight: 10
url: /hu/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
Ebben az oktatóanyagban megvizsgáljuk a mellékelt C# forráskódot, hogy beállíthassuk a tömörítési szintet egy dokumentum Aspose.Words for .NET használatával történő mentésekor. Ez a funkció lehetővé teszi a létrehozott dokumentum tömörítési szintjének szabályozását.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 Ebben a lépésben konfiguráljuk az OOXML mentési beállításokat a`OoxmlSaveOptions` osztály. Beállítottuk a tömörítési szintet`SuperFast` hogy gyorsabb legyen a tömörítés.

## 4. lépés: Mentse el a dokumentumot a megadott tömörítési szinttel

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Az utolsó lépésben a dokumentumot a`Save` metódust, és átadja a kimeneti fájl elérési útját a`.docx` kiterjesztést, a megadott mentési beállításokkal együtt.

Most már futtathatja a forráskódot a tömörítési szint beállításához a dokumentum mentésekor. Az eredményül kapott fájl a megadott könyvtárba kerül mentésre "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx" néven.

### Minta forráskód a tömörítési szint beállításához az Aspose.Words for .NET használatával 

```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a tömörítési szint beállításának funkcióját egy dokumentum Aspose.Words for .NET használatával történő mentésekor. A megfelelő tömörítési szint megadásával optimalizálhatja a dokumentum méretét és generálási sebességét.

 A`OoxmlSaveOptions` osztály rugalmasságot biztosít a tömörítési szint szabályozásához a`CompressionLevel` ingatlan megfelelő értékre, mint pl`SuperFast`. Ez lehetővé teszi, hogy megtalálja a megfelelő egyensúlyt a fájl mérete és a biztonsági mentési sebesség között az Ön egyedi igényei alapján.

A tömörítés használata előnyös lehet, ha csökkenteni kell a generált fájlok méretét, különösen nagy dokumentumok esetén. Ez megkönnyítheti a dokumentumok tárolását, megosztását és továbbítását.

Az Aspose.Words for .NET hatékony lehetőségeket és funkciókat kínál a dokumentumkezeléshez. A megfelelő biztonsági mentési beállítások használatával testreszabhatja a dokumentum-előállítási folyamatot, és optimalizálhatja az alkalmazás teljesítményét.

Nyugodtan fedezze fel az Aspose.Words for .NET további funkcióit a dokumentumgenerálási munkafolyamat javítása érdekében.
