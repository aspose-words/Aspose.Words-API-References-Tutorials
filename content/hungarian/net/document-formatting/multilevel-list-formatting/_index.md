---
title: Többszintű listaformázás Word dokumentumban
linktitle: Többszintű listaformázás Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan hozhat létre többszintű listát és hogyan alkalmazhat egyéni formázást Word-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/document-formatting/multilevel-list-formatting/
---
Ebben az oktatóanyagban bemutatjuk, hogyan használhatja a többszintű listaformázást a Word dokumentum funkciójában az Aspose.Words for .NET segítségével. Kövesse az alábbi lépéseket a forráskód megértéséhez és a módosítások alkalmazásához.

## 1. lépés: A dokumentum létrehozása és konfigurálása

Kezdésként hozzon létre egy új dokumentumot és egy kapcsolódó DocumentBuilder objektumot. Itt van, hogyan:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: A többszintű lista formázása

Most a többszintű listaformázást alkalmazzuk a DocumentBuilder objektumban elérhető módszerekkel. Itt van, hogyan:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## 3. lépés: A dokumentum mentése

 A szövegbeviteli űrlapmező beszúrása után mentse a dokumentumot a kívánt helyre a gombbal`Save` módszer. Ügyeljen arra, hogy megadja a megfelelő fájl elérési utat:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Példa forráskódra többszintű listaformázáshoz Aspose.Words for .NET használatával

Íme az Aspose.Words for .NET többszintű listaformázásának teljes forráskódja:


```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Ezzel a kóddal többszintű listát hozhat létre, és minden szinten megfelelő formázást alkalmazhat az Aspose.Words for .NET használatával.


## Következtetés

Ebben az oktatóanyagban megvizsgáltuk a többszintű listaformázási funkció használatának folyamatát egy Word-dokumentumban az Aspose.Words for .NET segítségével. A vázolt lépések követésével jól szervezett, több szintű listákat hozhat létre, javítva a dokumentumok szerkezetét és olvashatóságát.

### GYIK

#### K: Mi az a többszintű lista egy Word-dokumentumban?

V: A Word-dokumentumban lévő többszintű lista egy hierarchikus lista, amely lehetővé teszi az elemek különböző szintű alelemekbe rendezését. Segíti az információk strukturált bemutatását, megkönnyítve az olvasók számára a tartalom megértését.

#### K: Testreszabhatom a többszintű lista megjelenését?

V: Igen, testreszabhatja a többszintű lista megjelenését a Word-dokumentumban. Különböző stílusok, például felsorolásjelek, számok vagy betűk alkalmazásával, valamint a behúzás és a térköz módosításával tetszetős és rendezett listát hozhat létre.

#### K: Az Aspose.Words for .NET támogat más listaformázási beállításokat?

V: Igen, az Aspose.Words for .NET a lista formázásához nyújt átfogó szolgáltatáskészletet. Különféle listatípusokat támogat, beleértve a felsorolásjeles listákat, a számozott listákat és a többszintű listákat. Módosíthatja a listák formázását, hozzáadhat vagy eltávolíthat elemeket, és testreszabhatja a megjelenésüket.

#### K: Használhatom az Aspose.Words for .NET-et más dokumentumelemekkel való együttműködéshez?

V: Igen, az Aspose.Words for .NET kiterjedt lehetőségeket kínál különféle dokumentumelemekkel, például bekezdésekkel, táblázatokkal, képekkel stb. Lehetővé teszi Word-dokumentumok programozott létrehozását, módosítását és konvertálását, és egyszerűsíti a dokumentumfeldolgozási feladatokat.