---
title: Oda-vissza információk exportálása
linktitle: Oda-vissza információk exportálása
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató az oda-vissza információk exportálásához, amikor egy dokumentumot HTML-ként mentünk az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

Ebben az oktatóanyagban végigvezetjük a C#-forráskódon, amellyel az Aspose.Words for .NET segítségével exportálhatja az oda-vissza információkat egy dokumentumból. Ez a funkció lehetővé teszi, hogy az exportált HTML-fájlba körútra vonatkozó információkat is belefoglaljon, megkönnyítve az eredeti dokumentumon végrehajtott módosítások visszakeresését.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük a dokumentumot az exportáláshoz. A következő kóddal töltheti be a dokumentumot egy megadott könyvtárból:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ez a kód létrehozza a`Document` a dokumentum betöltésével a megadott könyvtárból.

## 3. lépés: HTML biztonsági mentési beállítások konfigurálása

Most konfiguráljuk a HTML mentési beállításokat a dokumentum körútinformációinak exportálására. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Ez a kód létrehozza a`HtmlSaveOptions`és beállítja a`ExportRoundtripInformation` opciót`true` hogy exportáláskor tartalmazza az oda-vissza útra vonatkozó információkat.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban beállított HTML mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Ez a kód konvertálja a dokumentumot HTML formátumba, beleértve a körútra vonatkozó információkat, és elmenti az exportált HTML-fájlt a megadott könyvtárba.

### Példa forráskód a Roundtrip Information exportáláshoz az Aspose.Words for .NET használatával


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Ügyeljen arra, hogy a dokumentumkönyvtár helyes elérési útját adja meg a`dataDir` változó.