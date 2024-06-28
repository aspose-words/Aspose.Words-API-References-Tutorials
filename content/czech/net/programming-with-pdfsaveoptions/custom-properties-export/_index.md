---
title: Export uživatelských vlastností v dokumentu PDF
linktitle: Export uživatelských vlastností v dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se exportovat uživatelské vlastnosti při převodu dokumentů do PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/custom-properties-export/
---

tomto tutoriálu vás provedeme kroky k exportu uživatelských vlastností dokumentu do dokumentu PDF pomocí Aspose.Words for .NET. Export uživatelských vlastností umožňuje zahrnout do vygenerovaného dokumentu PDF další informace. Postupujte podle následujících kroků:

## Krok 1: Vytvoření dokumentu a přidání uživatelských vlastností

Začněte vytvořením instance třídy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Krok 2: Přidejte vlastní vlastnosti
 Dále přidejte požadované uživatelské vlastnosti. Chcete-li například přidat vlastnost "Společnost" s hodnotou "Apose", použijte`Add` metoda kolekce CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Můžete přidat tolik vlastních vlastností, kolik potřebujete.

## Krok 3: Nastavte možnosti exportu PDF

Vytvořte instanci třídy PdfSaveOptions a určete, jak exportovat uživatelské vlastnosti:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Tato volba řídí export uživatelských vlastností při převodu do PDF.

## Krok 4: Převeďte dokument do PDF

 Použijte`Save` metoda převodu dokumentu do PDF s uvedením možností převodu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu pro uložení převedeného PDF.

### Příklad zdrojového kódu pro export uživatelských vlastností pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro export uživatelských vlastností z dokumentu pomocí Aspose.Words pro .NET:


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Podle těchto kroků můžete snadno exportovat uživatelské vlastnosti dokumentu při převodu do PDF pomocí Aspose.Words for .NET.


## Závěr

V tomto tutoriálu jsme vysvětlili, jak exportovat uživatelské vlastnosti z dokumentu do dokumentu PDF pomocí Aspose.Words for .NET. Podle popsaných kroků můžete do vygenerovaného dokumentu PDF snadno zahrnout další informace exportem uživatelských vlastností dokumentu. Využijte funkce Aspose.Words for .NET k přizpůsobení a obohacení dokumentů PDF exportem vlastních vlastností.

### Často kladené otázky

#### Otázka: Co je export uživatelských vlastností do dokumentu PDF?
Odpověď: Export uživatelských vlastností do dokumentu PDF umožňuje zahrnout do vygenerovaného dokumentu PDF další informace. Vlastní vlastnosti jsou metadata specifická pro váš dokument, jako jsou značky, klíčová slova nebo pověření. Exportem těchto uživatelských vlastností je můžete zpřístupnit uživatelům při prohlížení dokumentu PDF.

#### Otázka: Jak mohu exportovat uživatelské vlastnosti dokumentu do dokumentu PDF pomocí Aspose.Words for .NET?
Odpověď: Chcete-li exportovat uživatelské vlastnosti dokumentu do dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Vytvořte instanci souboru`Document` třída.

 Přidejte požadované uživatelské vlastnosti pomocí`CustomDocumentProperties` sbírka. Použijte například`Add` metoda pro přidání vlastnosti "Společnost" s hodnotou "Apose".

 Vytvořte instanci souboru`PdfSaveOptions` třídy a určete, jak exportovat uživatelské vlastnosti pomocí`CustomPropertiesExport` vlastnictví. The`PdfCustomPropertiesExport.Standard` value exportuje uživatelské vlastnosti podle výchozího nastavení.

 Použijte`Save` metoda`Document` třídy pro převod dokumentu do PDF s uvedením možností převodu.

#### Otázka: Jak mohu získat přístup k uživatelským vlastnostem dokumentu PDF?
Odpověď: Pro přístup k uživatelským vlastnostem dokumentu PDF můžete použít kompatibilní čtečku PDF, která podporuje zobrazení vlastností dokumentu. Většina běžných čteček PDF, jako je Adobe Acrobat Reader, poskytuje přístup k metadatům a vlastnostem dokumentu PDF. Tyto možnosti obvykle najdete v nabídce "Soubor" nebo kliknutím pravým tlačítkem na dokument a výběrem "Vlastnosti".