---
title: Pdf oldaltartomány betöltése
linktitle: Pdf oldaltartomány betöltése
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre egy adott PDF-oldaltartomány betöltéséhez az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Ebben az oktatóanyagban végigvezetjük, hogyan tölthet be egy adott oldaltartományt egy PDF-dokumentumból az Aspose.Words for .NET használatával. Kövesse az alábbi lépéseket:

## 1. lépés: PDF-oldalak tartományának betöltése

következő kóddal tölthet be egy adott oldaltartományt egy PDF-dokumentumból:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Ebben a példában a PDF dokumentum első oldalát töltjük be. Módosíthatja az értékeket`PageIndex`és`PageCount` a kívánt oldaltartományra.

## 2. lépés: A dokumentum mentése

 Végül elmentheti az adott oldaltartományt tartalmazó dokumentumot a`Save` módszer:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Ügyeljen arra, hogy a szerkesztett dokumentum mentéséhez megfelelő elérési utat adja meg.

Ez minden ! Most betöltött egy adott oldaltartományt egy PDF-dokumentumból az Aspose.Words for .NET használatával.

### Példa forráskódra a Pdf oldaltartományának betöltéséhez az Aspose.Words for .NET használatával

```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Ne felejtse el megadni a PDF-dokumentumok könyvtárának helyes elérési útját.



