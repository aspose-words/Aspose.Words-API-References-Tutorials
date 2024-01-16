---
title: Renderujte 3D DML 3D efekty v dokumentu PDF
linktitle: Renderujte 3D DML 3D efekty v dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak povolit vykreslování 3D DML efektů při převodu do PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

V tomto tutoriálu vás provedeme kroky k povolení vykreslování 3D DML efektů při převodu do PDF pomocí Aspose.Words for .NET. Tím se zachovají 3D efekty ve vygenerovaném dokumentu PDF. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu

Začněte nahráním dokumentu, který chcete převést do PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Nezapomeňte zadat správnou cestu k dokumentu.

## Krok 2: Nakonfigurujte možnosti uložení PDF

Vytvořte instanci třídy PdfSaveOptions a povolte pokročilé vykreslování 3D DML efektů:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Tato volba zachová 3D efekty ve vygenerovaném dokumentu PDF.

## Krok 3: Převeďte dokument do PDF

 Použijte`Save` způsob převodu dokumentu do PDF s uvedením možností uložení:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu pro uložení převedeného PDF.

### Příklad zdrojového kódu pro Dml 3DEffects Rendering pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Pomocí následujících kroků můžete snadno povolit vykreslování 3D DML efektů při převodu do PDF pomocí Aspose.Words for .NET.

## Závěr

tomto tutoriálu jsme vysvětlili, jak povolit vykreslování 3D DML efektů při převodu do PDF pomocí Aspose.Words for .NET. Podle popsaných kroků můžete snadno zachovat 3D efekty ve vygenerovaném dokumentu PDF. Tuto funkci použijte k zachování důležitých vizuálních efektů původního dokumentu.


### Často kladené otázky

#### Otázka: Co je vykreslování 3D DML efektů v dokumentu PDF?
Odpověď: Vykreslování 3D efektů DML v dokumentu PDF se týká schopnosti zachovat 3D efekty při převodu dokumentu do formátu PDF. To zachová vizuální efekty a zajistí, že vygenerovaný dokument PDF bude vypadat jako původní dokument.

#### Otázka: Jak mohu povolit vykreslování 3D DML efektů při převodu do PDF pomocí Aspose.Words for .NET?
Odpověď: Chcete-li povolit vykreslování 3D DML efektů při převodu do PDF pomocí Aspose.Words for .NET, postupujte takto:

 Vytvořte instanci souboru`Document` třídy určující cestu k dokumentu aplikace Word.

 Vytvořte instanci souboru`PdfSaveOptions` třídu a nastavte`Dml3DEffectsRenderingMode`majetek do`Dml3DEffectsRenderingMode.Advanced` umožňující pokročilé vykreslování 3D DML efektů.

 Použijte`Save` metoda`Document`třídy pro uložení dokumentu ve formátu PDF zadáním možností uložení.

#### Otázka: Jak mohu zkontrolovat, zda byly ve vygenerovaném dokumentu PDF vykresleny efekty 3D DML?
Odpověď: Chcete-li zkontrolovat, zda byly efekty 3D DML vykresleny ve vygenerovaném dokumentu PDF, otevřete soubor PDF v kompatibilním prohlížeči PDF, jako je Adobe Acrobat Reader, a prohlédněte si dokument. Měli byste vidět 3D efekty tak, jak se objevují v původním dokumentu.



