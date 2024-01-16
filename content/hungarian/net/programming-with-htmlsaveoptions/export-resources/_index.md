---
title: Erőforrások exportálása
linktitle: Erőforrások exportálása
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a dokumentumforrások exportálásához, ha HTML-ként menti az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/export-resources/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel a dokumentumforrásokat exportálhatja az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi az erőforrások, például a betűtípusok, külső fájlként történő exportálását, amikor egy dokumentumot HTML formátumban ment el.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük a dokumentumot az exportáláshoz. A következő kóddal töltheti be a dokumentumot egy megadott könyvtárból:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Ez a kód létrehozza a`Document` a dokumentum betöltésével a megadott könyvtárból.

## 3. lépés: A HTML biztonsági mentési beállítások konfigurálása

Most konfiguráljuk a HTML mentési beállításokat a dokumentum erőforrások exportálásához. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 Ez a kód létrehozza a`HtmlSaveOptions` és a következő beállításokat állítja be:

- `CssStyleSheetType` be van állítva`CssStyleSheetType.External` CSS-stíluslap exportálásához külső fájlba.
- `ExportFontResources` be van állítva`true` font erőforrások exportálásához.
- `ResourceFolder` megadja a célkönyvtárat, ahová az erőforrásokat menteni kell.
- `ResourceFolderAlias` Az erőforrásokhoz való hozzáféréshez használt URL-álnevet adja meg.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban beállított HTML mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Ez a kód a dokumentumot HTML formátumba konvertálja, és az erőforrásokat a megadott könyvtárba menti a megadott URL-alias használatával.

### Példa forráskódra az Aspose.Words for .NET használatával történő erőforrások exportálásához

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Ügyeljen arra, hogy a dokumentumkönyvtár helyes elérési útját adja meg a`dataDir` változó.