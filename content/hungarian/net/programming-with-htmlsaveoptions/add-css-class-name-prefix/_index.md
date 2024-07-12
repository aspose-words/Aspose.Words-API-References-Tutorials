---
title: Adja hozzá a Css osztálynév előtagot
linktitle: Adja hozzá a Css osztálynév előtagot
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a CSS-osztálynév előtag hozzáadásához, amikor egy dokumentumot HTML formátumba konvertál az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy hozzáadhasson egy CSS-osztálynév előtagot az Aspose.Words for .NET-hez. Ez a funkció lehetővé teszi, hogy egyéni előtagot adjon a generált CSS-osztálynevekhez, amikor egy dokumentumot HTML formátumba konvertál.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelyet HTML-be szeretnénk konvertálni. A dokumentum betöltéséhez használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Állítsa be a HTML mentési beállításokat

Most állítsuk be a HTML mentési beállításokat, beleértve a CSS-stíluslap típusát és a CSS-osztálynév előtagját. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Ez a kód létrehozza a`HtmlSaveOptions` és beállítja`CssStyleSheetType` nak nek`CssStyleSheetType.External`külső CSS stíluslap létrehozásához, és`CssClassNamePrefix` nak nek`"pfx_"` előtaghoz`"pfx_"` a CSS osztály megnevezésére.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban meghatározott HTML mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Ez a kód átalakítja a dokumentumot HTML formátumba, és elmenti egy fájlba, hozzáadva a CSS osztálynév előtaggal.

### Példa forráskódra a Css osztálynév előtag hozzáadása Aspose.Words for .NET használatával forráskódjához

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Most megtanulta, hogyan adhat hozzá CSS-osztálynév-előtagot egy dokumentum HTML-formátumba konvertálásakor az Aspose.Words for .NET használatával. Az ebben az oktatóanyagban található lépésenkénti útmutató lépéseit követve testreszabhatja a konvertált HTML-dokumentumokban lévő CSS-osztályneveket.