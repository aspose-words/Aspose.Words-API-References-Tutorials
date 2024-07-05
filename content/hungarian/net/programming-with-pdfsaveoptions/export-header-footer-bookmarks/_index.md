---
title: Word-dokumentum fejléc-lábléc könyvjelzőinek exportálása PDF-dokumentumba
linktitle: Word-dokumentum fejléc-lábléc könyvjelzőinek exportálása PDF-dokumentumba
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató Word-dokumentum fejléc-lábléc-könyvjelzőinek exportálásához PDF-dokumentum-könyvjelzőkbe az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Ez a cikk lépésről lépésre bemutatja, hogyan exportálhatja a Word-dokumentum fejléc-lábléc-könyvjelzőit pdf-dokumentum funkcióba az Aspose.Words for .NET segítségével. Részletesen elmagyarázzuk a kód minden részét. Az oktatóanyag végén megtudhatja, hogyan exportálhat könyvjelzőket egy dokumentum fejlécéből és láblécéből, és hogyan hozhat létre PDF-et a megfelelő könyvjelzőkkel.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Határozza meg a dokumentumkönyvtárat

 A kezdéshez meg kell határoznia annak a könyvtárnak az elérési útját, ahol a dokumentumok találhatók. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse fel a dokumentumot

Ezután be kell töltenünk a feldolgozni kívánt dokumentumot. Ebben a példában feltételezzük, hogy a dokumentum neve "Könyvjelzők a fejlécekben és láblécekben.docx", és a megadott dokumentumkönyvtárban található.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## 3. lépés: Konfigurálja a mentés PDF-ként opciókat

 A fejléc és lábléc könyvjelzők exportálásához konfigurálnunk kell a`PdfSaveOptions` tárgy. Ebben a példában az alapértelmezett könyvjelző vázlat szintjét 1-re, a fejléc és lábléc könyvjelző exportálási módját pedig "Első" értékre állítjuk.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## 4. lépés: Mentse el a dokumentumot PDF formátumban fejlécek és láblécek könyvjelzőivel

Végül elmenthetjük a dokumentumot PDF formátumban a korábban beállított mentési opciókkal.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Ez minden ! Sikeresen exportálta a fejléc- és lábléc-könyvjelzőket egy dokumentumból, és az Aspose.Words for .NET segítségével PDF-et hozott létre a megfelelő könyvjelzőkkel.

### Minta forráskód fejléc és lábléc könyvjelzők exportálásához az Aspose.Words for .NET segítségével

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan exportálhat fejléc- és lábléc-könyvjelzőket Word-dokumentumból PDF-dokumentumba az Aspose.Words for .NET használatával. Az exportált könyvjelzők egyszerű navigációt és gyors hivatkozást tesznek lehetővé a megfelelő fejlécekhez és láblécekhez a generált PDF-dokumentumban. Kövesse a leírt lépéseket a fejléc- és lábléc-könyvjelzők dokumentumból történő exportálásához, és a megfelelő könyvjelzőkkel rendelkező PDF-fájl létrehozásához az Aspose.Words for .NET segítségével. Ügyeljen arra, hogy megadja a dokumentumok helyes elérési útját, és szükség szerint konfigurálja a mentési beállításokat.

### Gyakran Ismételt Kérdések

### K: Mit jelent a fejléc- és lábléc-könyvjelzők exportálása Word-dokumentumból PDF-dokumentumba?
V: A fejléc- és lábléc-könyvjelzők exportálása Word-dokumentumból PDF-dokumentumba egy olyan szolgáltatás, amellyel a fej- és láblécekből könyvjelzőket tarthat és hozhat létre a PDF-dokumentumban. az eredeti Word-dokumentum láblécében. Ez lehetővé teszi a felhasználók számára, hogy gyorsan és egyszerűen navigálhassanak a PDF-dokumentumban a fejléceknek és lábléceknek megfelelő könyvjelzők használatával.

### K: Hogyan használhatom az Aspose.Words for .NET alkalmazást fejléc- és lábléc-könyvjelzők exportálására Word-dokumentumból PDF-dokumentumba?
V: A fejléc- és lábléc-könyvjelzők Word-dokumentumból PDF-dokumentumba történő exportálásához az Aspose.Words for .NET használatával, kövesse az alábbi lépéseket:

 Cseréléssel állítsa be a könyvtár elérési útját, ahol a dokumentumok találhatók`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

 Töltse be a feldolgozni kívánt dokumentumot a`Document` osztályt, és adja meg a Word dokumentum elérési útját a megadott dokumentumok könyvtárban.

 Konfigurálja a mentés PDF-ként opcióit a példány létrehozásával`PdfSaveOptions` osztályt, és állítsa be a megfelelő fejléc és lábléc könyvjelző beállításait.

 Mentse el a dokumentumot PDF formátumban a`Save` módszere a`Document` osztály, amely megadja az elérési utat és a mentési lehetőségeket.

### K: Milyen előnyökkel jár a fejléc- és lábléc-könyvjelzők PDF-dokumentumba exportálása?
V: A fejléc és lábléc könyvjelzők PDF-dokumentumba exportálásának előnyei a következők:

Egyszerű navigáció: A könyvjelzők segítségével a felhasználók könnyedén navigálhatnak a PDF-dokumentumokban meghatározott fejlécekre és láblécekre hivatkozva.

Gyorsreferencia: A könyvjelzők segítségével a felhasználók gyorsan megtalálhatják a PDF-dokumentum releváns részeit fejlécek és láblécek alapján.