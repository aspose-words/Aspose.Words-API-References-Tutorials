---
title: Ne mentse el a képet
linktitle: Ne mentse el a képet
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan tilthatja le a képsorok mentését Word dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

képjelek a Word-dokumentumok általánosan használt funkciói egyéni felsorolásjelek hozzáadásához. Bizonyos esetekben azonban szükség lehet a képsorok regisztrációjának letiltására, amikor a dokumentumokat az Aspose.Words Library for .NET segítségével kezeli. Ebben a részletes útmutatóban elmagyarázzuk, hogyan használhatja az Aspose.Words C# forráskódot a .NET-hez a DocSaveOptions mentési beállításainak használatával történő képsoros mentés letiltásához.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez, konvertálásához és védelméhez különböző platformokon, beleértve a .NET-et is. Számos funkciót kínál a dokumentumok kezeléséhez, például szöveg beszúrásához, formázás megváltoztatásához, szakaszok hozzáadásához és még sok máshoz.

## 1. lépés: A dokumentumkönyvtár beállítása

Az első lépés a könyvtár meghatározása, ahol a dokumentumok találhatók. Meg kell adnia a teljes könyvtár elérési utat. Például :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 2. lépés: Töltse be a dokumentumot képjelekkel

Ezután be kell töltenie a dokumentumot képjelekkel. Használja a Dokumentum osztályt a dokumentum fájlból való betöltéséhez. Például :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Ebben a példában a dokumentumot az "Image bullet points.docx" fájlból töltjük be.

  a dokumentumok könyvtárában található.

## 3. lépés: A rögzítési beállítások konfigurálása

Most konfiguráljuk a dokumentumunk mentési beállításait. A mentési beállítások megadásához használja a DocSaveOptions osztályt. Például :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

Ebben a példában létrehozunk egy új DocSaveOptions objektumot, és a SavePictureBullet tulajdonságot false értékre állítjuk a képsorok mentésének letiltásához.

## 4. lépés: Engedélyezze a „Ne mentse a képjelet” funkciót

A "Ne mentse a képjelet" funkció engedélyezéséhez már konfiguráltuk a mentési beállításokat úgy, hogy a SavePictureBullet false értékre van állítva. Ez biztosítja, hogy a képsorok ne kerüljenek mentésre a végleges dokumentumban.

## 5. lépés: Mentse el a dokumentumot

Végül elmentheti a dokumentumot a Dokumentum osztály Mentés metódusával. Adja meg a fájl teljes elérési útját és a kívánt fájlnevet. Például :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Ügyeljen arra, hogy a "dataDir" kifejezést lecserélje a dokumentumok könyvtárának elérési útjára.

## Példa forráskódra a DocSaveOptions mentési opciókhoz a "Ne mentse a képjelet" funkcióval az Aspose.Words for .NET használatával

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot képjelekkel
Document doc = new Document(dataDir + "Image bullet points.docx");

// Konfigurálja a mentési beállításokat a „Ne mentse a képsort” funkcióval
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Mentse el a dokumentumot a megadott opciókkal
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Következtetés

Ebben az útmutatóban bemutattuk, hogyan lehet letiltani a képsorok mentését egy dokumentumban a .NET Aspose.Words könyvtárával. A megadott lépések követésével és a mellékelt C# forráskód használatával könnyedén alkalmazhatja ezt a funkciót a C# alkalmazásban. A képsoros mentés letiltása bizonyos helyzetekben hasznos lehet a dokumentum szerkezetének és formázásának megőrzéséhez a képsorok mentése nélkül.