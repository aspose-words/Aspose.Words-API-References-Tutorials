---
title: Betűtípusnevek feloldása
linktitle: Betűtípusnevek feloldása
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a hiányzó betűtípusnevek megoldásához, amikor az Aspose.Words for .NET segítségével HTML-re konvertál.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy az Aspose.Words for .NET segítségével kijavítsa a hiányzó betűtípusneveket. Ez a funkció lehetővé teszi a hiányzó betűtípusnevek automatikus feloldását, amikor egy dokumentumot HTML formátumba konvertál.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük a feldolgozandó dokumentumot. A következő kóddal töltheti be a dokumentumot egy megadott könyvtárból:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Ez a kód létrehozza a`Document` a dokumentum betöltésével a megadott könyvtárból.

## 3. lépés: HTML biztonsági mentési beállítások konfigurálása

Most konfiguráljuk a HTML mentési beállításokat, hogy feloldjuk a konverzió során hiányzó betűtípusneveket. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Ez a kód létrehozza a`HtmlSaveOptions`és beállítja a`ResolveFontNames` opciót`true` hiányzó betűtípusnevek feloldásához HTML-re konvertáláskor. Továbbá a`PrettyFormat` opcióra van állítva`true` hogy szépen formázott HTML kódot kapjunk.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban beállított HTML mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Ez a kód a hiányzó betűtípusnevek automatikus feloldásával konvertálja a dokumentumot HTML formátumba, és a konvertált HTML-fájlt a megadott könyvtárba menti.

### Példa forráskódra a Resolve Font Names with Aspose.Words for .NET programhoz

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Ügyeljen arra, hogy a dokumentumkönyvtár helyes elérési útját adja meg a`dataDir` változó.