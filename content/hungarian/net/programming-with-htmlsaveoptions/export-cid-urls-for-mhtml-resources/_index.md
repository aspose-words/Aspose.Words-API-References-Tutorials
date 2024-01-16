---
title: Cid URL-ek exportálása Mhtml-forrásokhoz
linktitle: Cid URL-ek exportálása Mhtml-forrásokhoz
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre az MHTML-erőforrások CID URL-címeinek exportálásához, amikor egy dokumentumot ment az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel az Aspose.Words for .NET segítségével exportálhatja az MHTML-erőforrásokhoz tartozó CID URL-eket. Ez a funkció lehetővé teszi az MHTML-erőforrások CID URL-címeinek exportálását, amikor egy dokumentumot MHTML formátumban ment.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük a dokumentumot az exportáláshoz. A következő kóddal töltheti be a dokumentumot egy megadott könyvtárból:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Ez a kód létrehozza a`Document` a dokumentum betöltésével a megadott könyvtárból.

## 3. lépés: A HTML biztonsági mentési beállítások konfigurálása

Most beállítjuk a HTML mentési beállításokat az MHTML-erőforrások CID URL-címeinek exportálására. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Ez a kód létrehozza a`HtmlSaveOptions` a mentési formátum MHTML-re van állítva. Lehetővé teszi az MHTML-erőforrások CID URL-jeinek exportálását is beállítással`ExportCidUrlsForMhtmlResources` nak nek`true`.

## 4. lépés: A dokumentum konvertálása és mentése MHTML formátumba

Végül a dokumentumot MHTML-re konvertáljuk a korábban beállított HTML-mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Ez a kód MHTML-re konvertálja a dokumentumot, és egy fájlba menti az exportált MHTML-erőforrások CID URL-jeivel.

### Példa forráskód a Cid URL-ek exportálásához Mhtml erőforrásokhoz az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Ügyeljen arra, hogy a dokumentumkönyvtár helyes elérési útját adja meg a`dataDir` változó.

Most megtanulta, hogyan exportálhatja az MHTML-erőforrások CID URL-címeit, amikor egy dokumentumot MHTML formátumba ment az Aspose.Words for .NET használatával. Az ebben az oktatóanyagban található részletes útmutatót követve könnyedén kezelheti az exportált MHTML-dokumentumokban lévő CID URL-eket.

