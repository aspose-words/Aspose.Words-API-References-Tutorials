---
title: Převést dokument Word do PDF 1.7
linktitle: Převést dokument Word do PDF 1.7
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak převést dokument aplikace Word do formátu PDF 1.7 pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

tomto tutoriálu vás provedeme kroky, jak převést dokument aplikace Word do formátu PDF 1.7 pomocí Aspose.Words for .NET. Převod do PDF 1.7 vám umožňuje generovat soubory PDF, které odpovídají standardu PDF 1.7. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu

Začněte nahráním dokumentu, který chcete převést do PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Nezapomeňte zadat správnou cestu k dokumentu.

## Krok 2: Nastavte možnosti převodu PDF

Vytvořte instanci třídy PdfSaveOptions a zadejte verzi standardu PDF, který chcete použít:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Tato možnost zajišťuje, že vygenerovaný soubor PDF odpovídá standardu PDF 1.7.

## Krok 3: Převeďte dokument do PDF

 Použijte`Save` metoda převodu dokumentu do PDF s uvedením možností převodu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu pro uložení převedeného PDF.

### Příklad zdrojového kódu pro převod do PDF 17 pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód pro převod do PDF 1.7 pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Podle těchto kroků můžete snadno převést do PDF 1.7 pomocí Aspose.Words for .NET.


## Závěr

tomto tutoriálu jsme vysvětlili, jak převést dokument aplikace Word do formátu PDF 1.7 pomocí Aspose.Words for .NET. Podle popsaných kroků můžete snadno generovat soubory PDF, které vyhovují standardu PDF 1.7. Ujistěte se, že jste zadali správnou cestu k dokumentu aplikace Word a podle potřeby nakonfigurujte možnosti pro převod do PDF. Převod do PDF 1.7 zajišťuje optimální kompatibilitu a čitelnost na různých platformách.

### Často kladené otázky

#### Otázka: Co je převod Wordu na PDF 1.7?
Odpověď: Převod dokumentů aplikace Word do PDF 1.7 znamená generování souborů PDF, které odpovídají standardu PDF 1.7. Tato norma specifikuje funkce a požadavky na soubory PDF, což umožňuje optimální kompatibilitu a čitelnost na různých platformách.

#### Otázka: Jak mohu převést dokument aplikace Word do formátu PDF 1.7 pomocí Aspose.Words for .NET?
Odpověď: Chcete-li převést dokument aplikace Word do formátu PDF 1.7 pomocí Aspose.Words for .NET, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Načtěte dokument Word, který chcete převést do PDF, pomocí`Document` třídy a zadejte cestu k dokumentu aplikace Word v zadaném adresáři dokumentů.

 Nakonfigurujte převod jako možnosti PDF vytvořením instance souboru`PdfSaveOptions`třídy a zadáním verze standardu PDF, který chcete použít, pomocí`Compliance` nemovitost s hodnotou`PdfCompliance. Pdf17` vygenerovat soubor PDF, který odpovídá standardu PDF 1.7.

 Uložte dokument ve formátu PDF pomocí`Save` metoda`Document` třída určující cestu a možnosti uložení.

#### Otázka: Jaké jsou výhody převodu do PDF 1.7 pomocí Aspose.Words for .NET?
Odpověď: Výhody převodu do PDF 1.7 pomocí Aspose.Words pro .NET jsou:

Kompatibilita s PDF 1.7: Převod do PDF 1.7 zajišťuje, že vygenerovaný soubor PDF je kompatibilní s PDF 1.7, což zajišťuje kompatibilitu a čitelnost na různých platformách.

Zachování formátování dokumentu: Aspose.Words for .NET zajišťuje přesnou konverzi dokumentů Word zachováním formátování, obrázků a stylů, což vede k věrnému původnímu souboru PDF.