---
title: Képtömörítés PDF-dokumentumban
linktitle: Képtömörítés PDF-dokumentumban
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató a képek tömörítéséhez PDF-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/image-compression/
---

Ez a cikk lépésről lépésre bemutatja, hogyan használhatja a PDF-dokumentumban lévő képtömörítés funkciót az Aspose.Words for .NET-hez. Részletesen elmagyarázzuk a kód minden részét. Ennek az oktatóanyagnak a végén megértheti, hogyan lehet képeket tömöríteni egy dokumentumban, és hogyan hozhat létre PDF-et megfelelő képtömörítéssel.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Határozza meg a dokumentumkönyvtárat

 A kezdéshez meg kell határoznia annak a könyvtárnak az elérési útját, ahol a dokumentumok találhatók. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse fel a dokumentumot

Ezután be kell töltenünk a feldolgozni kívánt dokumentumot. Ebben a példában feltételezzük, hogy a dokumentum neve "Rendering.docx", és a megadott dokumentumkönyvtárban található.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. lépés: Konfigurálja a mentés PDF-ként opciókat képtömörítéssel

 A képek tömörítéséhez PDF-be konvertáláskor konfigurálnunk kell a`PdfSaveOptions` tárgy. Igény esetén beállíthatunk képtömörítési típust, JPEG minőséget és egyéb PDF megfelelőségi beállításokat.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## 4. lépés: Mentse el a dokumentumot PDF-ként képtömörítéssel

Végül elmenthetjük a dokumentumot PDF formátumban a korábban beállított mentési opciókkal.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## 5. lépés: Konfigurálja a képtömörítéssel PDF/A-2u formátumba történő mentés beállításait

Ha PDF/A-2u kompatibilis PDF-et szeretne létrehozni képtömörítéssel, konfigurálhatja a további mentési beállításokat.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Használjon 50%-os minőségű JPEG tömörítést a fájlméret csökkentéséhez.
};
```

## 6. lépés: Mentse el a dokumentumot PDF/A-2u formátumban képtömörítéssel

Mentse el a dokumentumot PDF/A-2u formátumban a korábban konfigurált további mentési beállításokkal.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Ez minden ! Sikeresen tömörítette a képeket egy dokumentumban, és megfelelő képtömörítéssel PDF-t hozott létre az Aspose.Words for .NET használatával.

### Minta forráskód képek tömörítéséhez az Aspose.Words for .NET segítségével

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // A fájlméret csökkentéséhez használjon 50%-os JPEG-tömörítést.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan tömöríthet képeket PDF-dokumentumban az Aspose.Words for .NET használatával. A leírt lépések követésével egyszerűen csökkentheti a PDF-dokumentumban lévő képek méretét, és megfelelő képtömörítéssel PDF-et hozhat létre. Használja az Aspose.Words for .NET képtömörítési funkcióit a PDF-dokumentumok méretének optimalizálásához a képminőség megőrzése mellett.

### Gyakran Ismételt Kérdések

#### K: Mit jelent a képtömörítés egy PDF-dokumentumban?
V: A PDF-dokumentumban lévő képek tömörítése a PDF-dokumentumban lévő képek méretének csökkentése érdekében a PDF-fájl teljes méretének csökkentése érdekében. Ez csökkenti a szükséges tárterületet, és javítja a teljesítményt a PDF betöltésekor és megtekintésekor.

#### K: Hogyan tömöríthetek képeket PDF-dokumentumban az Aspose.Words for .NET segítségével?
V: A képek PDF-dokumentumban való tömörítéséhez az Aspose.Words for .NET segítségével, kövesse az alábbi lépéseket:

 Hozzon létre egy példányt a`Document` osztály, amely megadja a Word dokumentum elérési útját.

 Hozzon létre egy példányt a`PdfSaveOptions` osztályt, és állítsa be a`ImageCompression`tulajdonát`PdfImageCompression.Jpeg` a JPEG tömörítés használatához.

Igényei szerint más képtömörítési beállításokat is beállíthat, például a JPEG minőséget.

 Használja a`Save` módszere a`Document`osztályba, hogy a dokumentumot PDF formátumba mentse a mentési beállítások megadásával.

#### K: Mi a különbség a szabványos képtömörítés és a PDF/A-2u képtömörítés között?
V: A szabványos képtömörítés csökkenti a PDF-dokumentumban lévő képek méretét, miközben megőrzi az űrlapmezőket. Ez csökkenti a PDF-fájl teljes méretét anélkül, hogy veszélyeztetné az űrlapmezők funkcióit.

képtömörítés PDF/A-2u-val egy további lehetőség, amely lehetővé teszi a PDF/A-2u szabványnak megfelelő PDF-fájl létrehozását képtömörítés alkalmazása mellett. A PDF/A-2u az archív PDF dokumentumok ISO szabványa, amely garantálja a dokumentumok hosszú távú megőrzését.
