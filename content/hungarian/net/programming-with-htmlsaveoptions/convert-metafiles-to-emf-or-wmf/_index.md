---
title: Konvertálja a metafájlokat EMF vagy Wmf formátumba
linktitle: Konvertálja a metafájlokat EMF vagy Wmf formátumba
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a metafájlok EMF vagy WMF formátumba konvertálásához, amikor egy dokumentumot HTML formátumba konvertál az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon a metafájlok EMF vagy WMF formátumba való konvertálásához az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a metafájl formátumú képek kompatibilisebb formátumokká, például EMF vagy WMF konvertálását, amikor egy dokumentumot HTML formátumba konvertál.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: Kép beszúrása a dokumentumba

Ebben a lépésben beszúrunk egy képet a konvertálandó dokumentumba. Használja a következő kódot egy kép beszúrásához egy adatforrásból HTML-címke használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Ez a kód létrehozza a`Document`és`DocumentBuilder` a dokumentum felépítéséhez. Beilleszt egy`<img>` címkét a dokumentumba egy base64 kódolású képpel.

## 3. lépés: Állítsa be a HTML mentési beállításokat

Most beállítjuk a HTML mentési beállításokat, beleértve a képekhez használandó metafájl formátumot. Használja a következő kódot:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Ez a kód létrehozza a`HtmlSaveOptions` és beállítja`MetafileFormat` nak nek`HtmlMetafileFormat.EmfOrWmf` megadni, hogy a metafájlokat EMF vagy WMF formátumba kell konvertálni a HTML formátumba konvertáláskor.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban meghatározott HTML mentési opciókkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Ez a kód konvertálja a dokumentumot HTML formátumba, és a konvertált metafájlokat tartalmazó fájlba menti EMF vagy WMF formátumban, a beállított mentési beállításoktól függően.

### Példa forráskód a metafájlok konvertálásához emf vagy wmf formátumba az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Ügyeljen arra, hogy a dokumentumkönyvtár helyes elérési útját adja meg a`dataDir` változó.

Most megtanulta, hogyan konvertálhat metafájlokat EMF vagy WMF formátumokká, amikor egy dokumentumot HTML formátumba konvertál az Aspose.Words for .NET használatával. Az oktatóanyagban található lépésenkénti útmutató követésével könnyedén kezelheti a konvertált HTML-dokumentumokban lévő metafájlokat.