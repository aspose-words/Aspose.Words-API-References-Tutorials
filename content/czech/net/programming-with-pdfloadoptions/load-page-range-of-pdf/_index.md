---
title: Načíst rozsah stránek Pdf
linktitle: Načíst rozsah stránek Pdf
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce načtením určitého rozsahu stránek PDF pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

V tomto tutoriálu vás provedeme tím, jak načíst konkrétní rozsah stránek z dokumentu PDF pomocí Aspose.Words for .NET. Postupujte podle následujících kroků:

## Krok 1: Načtení řady stránek PDF

načtení určitého rozsahu stránek z dokumentu PDF použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 V tomto příkladu načítáme první stránku dokumentu PDF. Můžete změnit hodnoty`PageIndex`a`PageCount` na požadovaný rozsah stránek.

## Krok 2: Uložení dokumentu

 Nakonec můžete uložit dokument obsahující konkrétní rozsah stránek pomocí`Save` metoda:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Nezapomeňte zadat správnou cestu k uložení upraveného dokumentu.

To je vše ! Nyní jste načetli konkrétní rozsah stránek z dokumentu PDF pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Load Page Range Of Pdf pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Nezapomeňte zadat správnou cestu k adresáři vašich dokumentů PDF.



