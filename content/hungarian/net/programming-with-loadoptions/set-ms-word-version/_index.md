---
title: Állítsa be az Ms Word verziót
linktitle: Állítsa be az Ms Word verziót
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan tölthet be dokumentumot az MS Word meghatározott verziójával az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-loadoptions/set-ms-word-version/
---
Amikor Word-dokumentumokat dolgoz fel egy C#-alkalmazásban, meg kell adni a Microsoft Word verzióját a dokumentum betöltésekor. A .NET Aspose.Words könyvtárával a LoadOptions segítségével egyszerűen beállíthatja, hogy az MS Word melyik verzióját használja. Ebben a lépésenkénti útmutatóban végigvezetjük, hogyan használhatja az Aspose.Words for .NET C# forráskódot az MS Word meghatározott verziójával a LoadOptions betöltési beállításaival egy dokumentum betöltésére.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez, konvertálásához és védelméhez különböző platformokon, beleértve a .NET-et is. Számos funkciót kínál a dokumentumok kezeléséhez, például szöveg beszúrásához, formázás megváltoztatásához, szakaszok hozzáadásához és még sok máshoz.

## Betöltési beállítások konfigurálása

Első lépésként konfiguráljuk a dokumentumunk betöltési beállításait. Használja a LoadOptions osztályt a betöltési paraméterek megadásához. Esetünkben az MswVersion tulajdonságot az MS Word kívánt verziójára kell beállítanunk. Például a Microsoft Word 2010-es verzióját használjuk. Íme, hogyan kell csinálni:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Létrehozunk egy új LoadOptions objektumot, és az MswVersion tulajdonságot MsWordVersion.Word2010 értékre állítjuk az MS Word 2010 verziójának megadásához.

## Dokumentum betöltése az MS Word megadott verziójával

Most, hogy konfiguráltuk a betöltési beállításokat, a Dokumentum osztály segítségével betölthetjük a dokumentumot, és megadhatjuk a betöltési beállításokat. Íme egy példa:

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Ebben a példában a dokumentumok könyvtárában található "Document.docx" dokumentumot töltjük be a megadott betöltési beállításokkal.

### Példa forráskód a LoadOptions "Set MS Word Version" funkcióval az Aspose.Words for .NET használatával

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurálja a betöltési beállításokat a "Set MS Word Version" funkcióval
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Töltse be a dokumentumot az MS Word megadott verziójával
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Mentse el a dokumentumot
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Következtetés

Ebben az útmutatóban elmagyaráztuk, hogyan tölthet fel egy dokumentumot, amely megadja az MS Word egy adott verzióját a .NET Aspose.Words könyvtárával. A megadott lépések követésével és a biztosított C# kód használatával könnyedén alkalmazhatja ezt a funkciót a C# alkalmazásban. Ha egy dokumentumot az MS Word meghatározott verziójával tölt be, akkor biztosíthatja a dokumentum megfelelő kompatibilitását és feldolgozását az alkalmazásban.


### GYIK

#### K: Miért kell megadnom az MS Word verzióját, amikor egy dokumentumot betöltek egy C# alkalmazásba?

Az MS Word verziójának megadása biztosítja a dokumentum megfelelő betöltését és feldolgozását, különösen akkor, ha speciális formázással vagy funkciókkal foglalkozik, amelyek a különböző verziók között változhatnak.

#### K: Az MS Word mely verzióit támogatja az Aspose.Words?

V: Az Aspose.Words for .NET támogatja az MS Word különféle verzióit, beleértve a Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 és még sok mást.

#### K: Betölthetek-e egy dokumentumot az MS Word más verziójával, mint amelyik a rendszeremre van telepítve?

V: Igen, az Aspose.Words lehetővé teszi az MS Word más verziójának megadását a dokumentum betöltésekor, így biztosítva a kompatibilitást akkor is, ha a célrendszernek más az MS Word verziója.

#### K: Milyen előnyökkel jár az MS Word verzió beállítása a C# alkalmazásomban?

V: Az MS Word verzió beállítása biztosítja, hogy a dokumentum az adott verzió tervezett formázása és jellemzői szerint kerüljön feldolgozásra, következetes kimenetet biztosítva.

#### K: Az Aspose.Words csak DOCX dokumentumok kezelésére korlátozódik?

V: Nem, az Aspose.Words különféle dokumentumformátumokat támogat, beleértve a DOC-t, az RTF-et, a HTML-t, a PDF-t és még sok mást, így sokoldalú eszköz a különböző típusú dokumentumok kezelésére.