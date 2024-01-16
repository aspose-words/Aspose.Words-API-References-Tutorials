---
title: Kétirányú jelek hozzáadása a Word dokumentumhoz
linktitle: Kétirányú jelek hozzáadása a Word dokumentumhoz
second_title: Aspose.Words Document Processing API
description: Tanuljon meg kétirányú jelöléseket hozzáadni egy Word-dokumentumhoz az Aspose.Words for .NET segítségével, és készítsen professzionális többnyelvű dokumentumokat.
type: docs
weight: 10
url: /hu/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Az Aspose.Words for .NET egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez C# alkalmazásokban. Az Aspose.Words által kínált szolgáltatások közé tartozik az a képesség, hogy kétirányú (kétirányú) jelöléseket adjon a dokumentumhoz. Ebben az útmutatóban végigvezetjük, hogyan használhatja az Aspose.Words for .NET C# forráskódját kétirányú jelölések hozzáadásához egy dokumentumhoz.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy népszerű könyvtár, amely egyszerűvé és hatékonysá teszi a Word-dokumentumokkal végzett szövegfeldolgozást. A funkciók széles skáláját kínálja a Word-dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez, beleértve a kétirányú jelölések hozzáadását.

## A dokumentum létrehozása és tartalom hozzáadása

Az első lépés egy új dokumentum létrehozása és tartalom hozzáadása. Új dokumentumpéldány létrehozásához használja a Dokumentum osztályt. Ezután a DocumentBuilder osztály segítségével szöveget adjon a dokumentumhoz. Íme egy példa:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

Ebben a példában új dokumentumot hozunk létre, és a DocumentBuilder segítségével szöveget adunk hozzá. Három sornyi szöveget adtunk hozzá: egyet angolul, egyet héberül és egyet arabul, hogy bemutassuk a tartalom hozzáadását különböző nyelveken.

## Kétirányú jelek hozzáadva

A tartalom hozzáadása után most már kétirányú jeleket is hozzáadhatunk a dokumentumhoz. Ehhez a TxtSaveOptions osztályt használjuk, és az AddBidiMarks tulajdonságot igazra állítjuk. Itt van, hogyan:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Ebben a példában létrehozzuk a TxtSaveOptions egy példányát, és az AddBidiMarks tulajdonságot igazra állítjuk. Ezután a Dokumentum osztály Mentés metódusával mentjük a dokumentumot kétirányú jelölésekkel.

### Példa forráskód az "Add Bidi Marks" funkcióhoz az Aspose.Words for .NET-hez

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozzon létre egy dokumentumot, és adjon hozzá tartalmat
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Adjon hozzá kétirányú jeleket
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Következtetés

Ebben az útmutatóban elmagyaráztuk, hogyan használhatja az Aspose.Words for .NET-et kétirányú jelölések hozzáadásához egy Word-dokumentumhoz a mellékelt C# forráskód használatával. A megadott lépések követésével könnyedén hozzáadhat Bidi jeleket a Word dokumentumaihoz a C# alkalmazásban. Az Aspose.Words óriási rugalmasságot és teljesítményt kínál a szövegszerkesztéshez szövegformázással és nyelvkezeléssel, lehetővé téve a többnyelvű dokumentumok professzionális létrehozását.

### Gyakran Ismételt Kérdések

#### K: Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez C# alkalmazásokban. Számos funkciót kínál a Word-dokumentumokkal végzett szövegfeldolgozáshoz, beleértve a kétirányú (kétirányú) jelölések hozzáadását.

#### K: Milyen funkciókat kínál az Aspose.Words for .NET?
Az Aspose.Words for .NET szolgáltatások széles skáláját kínálja Word-dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez. Néhány ilyen funkció közé tartozik a dokumentumok létrehozása, tartalom hozzáadása, szöveg formázása, táblázatok kezelése, dokumentumok egyesítése és felosztása, dokumentumok konvertálása stb.

#### K: Hogyan adhatok kétirányú jeleket egy Word-dokumentumhoz az Aspose.Words for .NET használatával?
Az alábbi lépések végrehajtásával kétirányú jelöléseket adhat a Word-dokumentumokhoz:

 Hozzon létre egy új dokumentumot a`Document` osztály.

 Használja a`DocumentBuilder` osztályt, hogy tartalmat adjon a dokumentumhoz.

 Miután hozzáadta a tartalmat, használja a`TxtSaveOptions` osztályt, és állítsa be a`AddBidiMarks`tulajdonát`true`.

 Mentse el a dokumentumot kétirányú jelekkel a`Save` módszere a`Document` osztály.

#### K: Az Aspose.Words több nyelvet is támogat kétirányú jelölések hozzáadásához?
Igen, az Aspose.Words több nyelvet is támogat a kétirányú jelölések hozzáadásához. Az Aspose.Words for .NET segítségével kétirányú jelöléseket adhat hozzá a különböző nyelvű szövegekhez, például angolul, héberül és arabul.

#### K: Vannak további lehetőségek a dokumentum kétirányú jelöléssel történő mentésére?
 Igen, megadhat más beállításokat is, ha a dokumentumot kétirányú jelöléssel menti a segítségével`TxtSaveOptions` osztály. Például beállíthatja a dokumentum mentési formátumát, a kódolási beállításokat stb.