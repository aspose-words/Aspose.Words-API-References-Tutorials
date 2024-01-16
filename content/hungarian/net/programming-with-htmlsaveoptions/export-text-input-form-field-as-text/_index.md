---
title: Szövegbeviteli űrlapmező exportálása szövegként
linktitle: Szövegbeviteli űrlapmező exportálása szövegként
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató a szövegbeviteli űrlapmezők egyszerű szövegként történő exportálásához az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, amellyel a szövegbeviteli űrlapmezőket egyszerű szövegként exportálhatja az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi, hogy a szövegbeviteli űrlapmezőket olvasható szövegként exportálja, ahelyett, hogy HTML beviteli elemként exportálná őket.

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

Most beállítjuk a HTML mentési beállításokat a szövegbeviteli űrlapmezők egyszerű szövegként történő exportálásához. Használja a következő kódot:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// A megadott mappának léteznie kell, és üresnek kell lennie.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Ez a kód létrehozza a`HtmlSaveOptions`és beállítja a`ExportTextInputFormFieldAsText` opciót`true` szövegbeviteli űrlapmezők egyszerű szövegként történő exportálásához. Ezenkívül meghatározza azt a mappát, ahová a kibontott képeket menti.

## 4. lépés: A dokumentum konvertálása és mentése HTML formátumba

Végül a dokumentumot HTML formátumba konvertáljuk a korábban beállított HTML mentési beállításokkal. Használja a következő kódot:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Ez a kód a szövegbeviteli űrlapmezőket egyszerű szövegként exportálva HTML-formátumba konvertálja a dokumentumot, és elmenti az exportált HTML-fájlt a megadott könyvtárba.

### Példa forráskódra a Szövegbeviteli űrlap mező szövegként történő exportálásához az Aspose.Words for .NET használatával


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// A megadott mappának léteznie kell, és üresnek kell lennie.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Állítsa be az űrlapmezők egyszerű szövegként, nem pedig HTML beviteli elemként történő exportálását.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Ügyeljen arra, hogy a dokumentumkönyvtár helyes elérési útját adja meg a`dataDir` változó.