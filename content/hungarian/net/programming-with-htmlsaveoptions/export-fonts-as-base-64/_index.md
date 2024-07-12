---
title: Betűtípusok exportálása alapként 64
linktitle: Betűtípusok exportálása alapként 64
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató a 64-es alapbetűtípusok exportálásához, amikor a dokumentumot Aspose.Words for .NET segítségével menti.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel 64-es alapbetűtípusokat exportálhat az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a betűtípusok exportálását 64-es alapadatként, amikor egy dokumentumot HTML formátumban ment el.

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

Most konfiguráljuk a HTML mentési beállításokat az alap 64-es betűtípusok exportálására. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Ez a kód létrehozza a`HtmlSaveOptions` és beállítja`ExportFontsAsBase64` nak nek`true` megadni, hogy a betűtípusokat 64-es alapadatként kell exportálni HTML-ként történő mentéskor.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban beállított HTML mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Ez a kód konvertálja a dokumentumot HTML formátumba, és egy fájlba menti a 64-es alapadatként exportált betűtípusokkal.

### Példa forráskód az Export Fonts As Base 64-hez az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Ügyeljen arra, hogy a dokumentumkönyvtár helyes elérési útját adja meg a`dataDir` változó.

Most megtanulta, hogyan exportálhat 64-es alapbetűtípusokat, amikor egy dokumentumot HTML-ként ment el az Aspose.Words for .NET használatával. Az oktatóanyag lépésenkénti útmutatójának követésével könnyedén exportálhatja a betűtípusokat biztonságosan és beágyazva a HTML-dokumentumokba.