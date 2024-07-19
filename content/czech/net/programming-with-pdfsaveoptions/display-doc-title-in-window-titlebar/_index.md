---
title: Zobrazení názvu dokumentu v záhlaví okna
linktitle: Zobrazení názvu dokumentu v záhlaví okna
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zobrazit název dokumentu v záhlaví okna při převodu do PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

tomto tutoriálu vás provedeme kroky k zobrazení názvu dokumentu v záhlaví okna pomocí Aspose.Words for .NET. Tato funkce umožňuje zobrazit název dokumentu v záhlaví okna, když otevřete vygenerovaný dokument PDF. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu

Začněte nahráním dokumentu, který chcete převést do PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Nezapomeňte zadat správnou cestu k dokumentu.

## Krok 2: Nakonfigurujte možnosti uložení PDF

Vytvořte instanci třídy PdfSaveOptions a povolte zobrazení názvu dokumentu v záhlaví okna:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Tato volba umožňuje zobrazení názvu dokumentu v záhlaví okna při převodu do PDF.

## Krok 3: Převeďte dokument do PDF

 Použijte`Save` metoda převodu dokumentu do PDF s uvedením možností převodu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu pro uložení převedeného PDF.

### Příklad zdrojového kódu pro zobrazení názvu dokumentu v záhlaví okna pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro zobrazení názvu dokumentu v záhlaví okna v dokumentu PDF s Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Podle těchto kroků můžete snadno zobrazit název dokumentu v záhlaví okna při převodu do PDF pomocí Aspose.Words for .NET.

### Často kladené otázky

#### Otázka: Co je funkce "Zobrazit název dokumentu v záhlaví okna" s Aspose.Words pro .NET?
Funkce "Zobrazit název dokumentu v záhlaví okna" s Aspose.Words for .NET vám umožňuje zobrazit název dokumentu v záhlaví okna, když otevřete vygenerovaný dokument PDF. To usnadňuje identifikaci a rozlišení dokumentů PDF ve vašem prostředí pro čtení.

#### Otázka: Jak mohu použít tuto funkci s Aspose.Words pro .NET?
Chcete-li použít tuto funkci s Aspose.Words pro .NET, postupujte takto:

 Vložte dokument pomocí`Document` a zadáním cesty k souboru, který se má převést do PDF.

 Nakonfigurujte možnosti uložení PDF vytvořením instance souboru`PdfSaveOptions` třídy a nastavení`DisplayDocTitle`majetek do`true`. To umožňuje zobrazení názvu dokumentu v záhlaví okna při převodu do PDF.

 Použijte`Save` způsob převodu dokumentu do PDF s uvedením možností převodu.

#### Otázka: Mění tato funkce obsah samotného dokumentu?
Ne, tato funkce nemění obsah samotného dokumentu. Ovlivňuje pouze zobrazení názvu dokumentu v záhlaví okna, když je otevřen jako dokument PDF. Obsah dokumentu zůstává nezměněn.

#### Otázka: Je možné upravit název dokumentu zobrazeného v záhlaví okna?
 Ano, můžete upravit název dokumentu zobrazený v záhlaví okna změnou`Document.Title` vlastnost dokumentu před převodem do PDF. Požadovaný titul můžete nastavit pomocí řetězce. Před voláním se ujistěte, že jste nastavili název`Save` způsob převodu do PDF.

#### Otázka: Jaké další výstupní formáty podporuje Aspose.Words pro převod dokumentů?
Aspose.Words for .NET podporuje mnoho výstupních formátů pro převod dokumentů, jako jsou PDF, XPS, HTML, EPUB, MOBI, obrázky (JPEG, PNG, BMP, TIFF, GIF) a mnoho dalších. ještě další. Můžete si vybrat vhodný výstupní formát podle vašich konkrétních potřeb.