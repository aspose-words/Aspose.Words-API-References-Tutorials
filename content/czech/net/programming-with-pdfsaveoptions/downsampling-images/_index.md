---
title: Zmenšete velikost dokumentu PDF pomocí převzorkování obrázků
linktitle: Zmenšete velikost dokumentu PDF pomocí převzorkování obrázků
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zmenšit velikost dokumentu PDF pomocí převzorkování obrázků při převodu do PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/downsampling-images/
---

V tomto tutoriálu vás provedeme kroky ke zmenšení velikosti dokumentu PDF pomocí převzorkování obrázků při převodu do PDF pomocí Aspose.Words for .NET. Tím se zmenší velikost generovaného souboru PDF. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu

Začněte nahráním dokumentu, který chcete převést do PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Nezapomeňte zadat správnou cestu k dokumentu.

## Krok 2: Nakonfigurujte možnosti uložení PDF

Vytvořte instanci třídy PdfSaveOptions a nastavte možnosti zmenšení obrázku:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 The`Resolution` vlastnost určuje cílové rozlišení obrázků a`ResolutionThreshold`Vlastnost určuje minimální rozlišení, pod kterým nebudou obrázky zmenšeny.

## Krok 3: Převeďte dokument do PDF

 Použijte`Save` způsob převodu dokumentu do PDF s uvedením možností uložení:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu pro uložení převedeného PDF.

### Příklad zdrojového kódu pro převzorkování obrázků pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Můžeme nastavit minimální práh pro downsampling.
	// Tato hodnota zabrání převzorkování druhého obrázku ve vstupním dokumentu.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Pomocí těchto kroků můžete snadno snížit rozlišení obrazu při převodu do PDF pomocí Aspose.Words for .NET.

## Závěr

tomto tutoriálu jsme vysvětlili, jak zmenšit velikost dokumentu PDF pomocí vzorkování obrázků při převodu do PDF pomocí Aspose.Words for .NET. Podle popsaných kroků můžete snadno snížit rozlišení obrázků a velikost generovaného souboru PDF. Ujistěte se, že jste zadali správnou cestu k dokumentu a podle potřeby nakonfigurujte možnosti vzorkování obrazu. Zmenšení velikosti souboru PDF usnadňuje sdílení, ukládání a rychlé načítání souboru na různých platformách. Užijte si výhody zmenšení velikosti dokumentu PDF pomocí vzorkování obrázků pomocí Aspose.Words for .NET.

### Často kladené otázky

#### Otázka: Co snižuje velikost dokumentu PDF pomocí vzorkování obrázku?
Odpověď: Zmenšení velikosti dokumentu PDF pomocí vzorkování obrázků znamená zmenšení velikosti generovaného souboru PDF snížením rozlišení obrázků při převodu do PDF. To optimalizuje využití úložného prostoru a usnadňuje sdílení a přenos souboru PDF.

#### Otázka: Jak mohu zmenšit velikost dokumentu PDF pomocí vzorkování obrázků pomocí Aspose.Words for .NET?
Odpověď: Chcete-li zmenšit velikost dokumentu PDF pomocí vzorkování obrázků pomocí Aspose.Words for .NET, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Načtěte dokument, který chcete převést do PDF, pomocí`Document` třídy a zadejte cestu k dokumentu v zadaném adresáři dokumentů.

 Nakonfigurujte možnosti uložení jako PDF vytvořením instance souboru`PdfSaveOptions` třídy a nastavením možností vzorkování obrazu pomocí`DownsampleOptions` vlastnictví. Cílové rozlišení obrázků můžete určit pomocí`Resolution` a nastavte minimální práh rozlišení, nad kterým nebudou obrázky zmenšeny pomocí`ResolutionThreshold` vlastnictví.

 Uložte dokument ve formátu PDF pomocí`Save` metoda`Document` třída určující cestu a možnosti uložení.

#### Otázka: Jaké jsou výhody zmenšení velikosti dokumentu PDF pomocí vzorkování obrázků?
Odpověď: Výhody zmenšení velikosti dokumentu PDF pomocí vzorkování obrázků jsou:

Zmenšená velikost souboru PDF: Vzorkování obrázků snižuje rozlišení obrázků v dokumentu PDF, což má za následek výrazné snížení velikosti souboru PDF. To usnadňuje sdílení a přenos souboru, zejména prostřednictvím e-mailu nebo online.

Optimalizace úložného prostoru: Zmenšení velikosti souboru PDF pomáhá optimalizovat využití úložného prostoru, zejména pokud máte mnoho souborů PDF obsahujících obrázky s vysokým rozlišením.

Zlepšení výkonu: Menší soubory PDF se načítají rychleji a lze je rychleji otevřít a prohlížet na různých zařízeních.