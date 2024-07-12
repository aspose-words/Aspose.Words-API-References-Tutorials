---
title: Konvertálja a metafájlokat SVG formátumba
linktitle: Konvertálja a metafájlokat SVG formátumba
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a metafájlok SVG formátumba konvertálásához, amikor egy dokumentumot HTML formátumba konvertál az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel metafájlokat konvertálhat SVG formátumba az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a metafájlok SVG formátumba konvertálását, amikor egy dokumentumot HTML formátumba konvertál.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: SVG-kép beszúrása a dokumentumba

Ebben a lépésben beszúrunk egy SVG képet a konvertálandó dokumentumba. Használja a következő kódot SVG-kép beszúrásához HTML-címke használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Ez a kód létrehozza a`Document`és`DocumentBuilder` a dokumentum felépítéséhez. Beilleszti a`<svg>` címke, amely a`<polygon>` elem attribútumokkal az SVG-kép alakjának és stílusának meghatározásához.

## 3. lépés: Állítsa be a HTML mentési beállításokat

Most beállítjuk a HTML mentési beállításokat, megadva, hogy a metafájlokat SVG formátumba kell konvertálni. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Ez a kód létrehozza a`HtmlSaveOptions` és beállítja`MetafileFormat` nak nek`HtmlMetafileFormat.Svg` megadni, hogy a metafájlokat SVG formátumba kell konvertálni a HTML formátumba konvertáláskor.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban meghatározott HTML mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Ez a kód a dokumentumot HTML formátumba konvertálja, és egy fájlba menti, amelyben a metafájlok SVG formátumba lettek konvertálva.

### Példa forráskód a metafájlok konvertálásához SVG-be az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
