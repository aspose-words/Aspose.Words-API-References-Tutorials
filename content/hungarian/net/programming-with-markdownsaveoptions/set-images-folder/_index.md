---
title: Képek mappa beállítása
linktitle: Képek mappa beállítása
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan állíthatja be a képek mappáját, amikor az Aspose.Words for .NET segítségével Markdownba exportál. Testreszabhatja a képek elhelyezését a jobb rendszerezés és integráció érdekében.
type: docs
weight: 10
url: /hu/net/programming-with-markdownsaveoptions/set-images-folder/
---

Íme egy lépésről lépésre bemutatott útmutató a következő C# forráskódhoz, amely segít beállítani a képmappákat a Markdown exportálási beállításaihoz az Aspose.Words könyvtár .NET-hez segítségével. A kód használata előtt győződjön meg arról, hogy az Aspose.Words könyvtárat belefoglalta a projektbe.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ügyeljen arra, hogy megadja a dokumentumok könyvtárának megfelelő elérési útját, ahol a képeket tartalmazó dokumentum található.

## 2. lépés: Töltse be a képeket tartalmazó dokumentumot

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

A Markdown opciókkal betöltjük a megadott dokumentumot, amely az exportálni kívánt képeket tartalmazza.

## 3. lépés: Állítsa be a képek mappáját a Markdown exportálási opcióihoz

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Létrehozunk egy példányt`MarkdownSaveOptions` és a segítségével állítsa be a képek mappa elérési útját`ImagesFolder` ingatlan. Ügyeljen arra, hogy megadja annak a mappának a helyes elérési útját, ahová menteni szeretné az exportált képeket.

## 4. lépés: Mentse el a dokumentumot a Markdown exportálási beállításokkal

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

A dokumentumot a megadott Markdown exportálási beállításokkal egy memóriafolyamba mentjük. Ezután a folyamatot más műveletek végrehajtására használhatja, például a Markdown tartalmat fájlba mentheti.

### Példa forráskódra a MarkdownSaveOptions képmappa beállításához az Aspose.Words for .NET segítségével

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Ez a forráskód bemutatja, hogyan tölthet be képeket tartalmazó dokumentumot, majd hogyan állíthatja be a képek mappáját a Markdown exportálási beállításaihoz. A megadott opciók használatával a dokumentumot a rendszer egy memóriafolyamba menti. Ez lehetővé teszi a képek mappa helyének testreszabását Markdown tartalom exportálásakor.