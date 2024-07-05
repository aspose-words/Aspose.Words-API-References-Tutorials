---
title: Raszterizálja az átalakított elemeket
linktitle: Raszterizálja az átalakított elemeket
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan tilthatja le az átalakított elemek raszterezését, amikor az Aspose.Words for .NET segítségével PCL formátumba konvertál.
type: docs
weight: 10
url: /hu/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Az Aspose.Words for .NET egy hatékony könyvtár Word-dokumentumok létrehozására, kezelésére és konvertálására C#-alkalmazásokban. Az Aspose.Words által kínált szolgáltatások közé tartozik az átalakított elemek raszterizálásának lehetősége a dokumentumok különböző formátumokba konvertálásakor. Ebben az útmutatóban bemutatjuk, hogyan használhatja az Aspose.Words for .NET C# forráskódját az átalakított elemek raszterizálásának letiltásához, amikor egy dokumentumot PCL formátumba konvertál.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy népszerű könyvtár, amely egyszerűvé és hatékonysá teszi a Word-dokumentumokkal végzett szövegfeldolgozást. Funkciók széles skáláját kínálja Word-dokumentumok létrehozásához, szerkesztéséhez és konvertálásához, beleértve az átalakított elemek raszterizálásának támogatását az átalakítás során.

## Word dokumentum betöltése

Az első lépés a PCL formátumba konvertálni kívánt Word dokumentum betöltése. A Dokumentum osztály segítségével töltse be a dokumentumot a forrásfájlból. Íme egy példa:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Ebben a példában a dokumentumok könyvtárában található "Rendering.docx" dokumentumot töltjük be.

## Biztonsági mentési beállítások konfigurálása

A következő lépés a PCL formátumba konvertálás mentési beállításainak konfigurálása. Használja a PclSaveOptions osztályt, és állítsa a RasterizeTransformedElements tulajdonságot false értékre. Íme, hogyan kell csinálni:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Létrehozunk egy új PclSaveOptions objektumot, és a SaveFormat tulajdonságot SaveFormat.Pcl értékre állítjuk annak megadásához, hogy PCL formátumban akarjuk menteni a dokumentumot. Ezután a RasterizeTransformedElements tulajdonságot false értékre állítjuk az átalakított elemek raszterezésének letiltásához.

## A dokumentum konvertálása PCL formátumba

Most, hogy konfiguráltuk a mentési beállításokat, folytathatjuk a dokumentum PCL formátumba való konvertálását. Használja a Dokumentum osztály Mentés metódusát a konvertált dokumentum PCL formátumba mentéséhez a mentési beállítások megadásával. Íme egy példa:

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

Ebben a példában a konvertált dokumentumot "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" néven mentjük a megadott mentési beállítások használatával.

### Példa forráskódra az Aspose.Words for .NET "Raszterize Transformed Elements" funkciójához

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a Word dokumentumot


Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurálja a biztonsági mentési beállításokat a PCL formátumra való átalakításhoz
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Konvertálja a dokumentumot PCL formátumba
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Következtetés

Ebben az útmutatóban bemutattuk, hogyan használhatja az Aspose.Words for .NET-et az átalakított elemek raszterezésének letiltására, amikor egy dokumentumot PCL formátumba konvertál a mellékelt C# forráskód használatával. A megadott lépések követésével könnyedén szabályozhatja az átalakított elemek raszterezési viselkedését, amikor Word-dokumentumait különböző formátumokba konvertálja. Az Aspose.Words óriási rugalmasságot és teljesítményt kínál az átalakított elemekkel való munkavégzéshez, lehetővé téve, hogy pontosan az Ön egyedi igényei szerint hozzon létre konvertált dokumentumokat.