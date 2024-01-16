---
title: Zmenšete velikost souboru PDF nevkládáním základních písem
linktitle: Zmenšete velikost souboru PDF nevkládáním základních písem
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zmenšit velikost souboru PDF nevkládáním základních písem při převodu dokumentů Wordu do PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

V tomto tutoriálu vás provedeme kroky, jak zmenšit velikost souboru PDF tím, že do Aspose.Words for .NET nevkládáte základní písma. Tato funkce umožňuje řídit, zda při převodu dokumentu aplikace Word musí být do PDF vložena základní písma jako Arial, Times New Roman atd. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu

Začněte nahráním dokumentu aplikace Word, který chcete převést do formátu PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Nezapomeňte zadat správnou cestu k dokumentu aplikace Word.

## Krok 2: Nastavte možnosti převodu PDF

Vytvořte instanci třídy PdfSaveOptions a povolte základní zamezení vkládání písem:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Tato volba určuje, zda mají být základní písma vložena do PDF, nebo ne.

## Krok 3: Převeďte dokument do PDF

 Použijte`Save` způsob převodu dokumentu aplikace Word do formátu PDF zadáním možností převodu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu pro uložení převedeného PDF.

### Příklad zdrojového kódu pro Avoid Embedding Core Fonts pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro použití této funkce, abyste se vyhnuli vkládání základních písem pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Výstupní PDF nebude vloženo základními fonty, jako je Arial, Times New Roman atd.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Pomocí těchto kroků můžete snadno určit, zda mají být základní písma vložena do PDF při převodu dokumentu aplikace Word pomocí Aspose.Words for .NET.


## Závěr

tomto tutoriálu jsme vysvětlili, jak zmenšit velikost souboru PDF tím, že do Aspose.Words for .NET nevkládáte základní písma. Tato funkce vám umožňuje řídit, zda mají být základní písma vložena do PDF při převodu dokumentu aplikace Word. Podle uvedených kroků můžete snadno ovládat vkládání nebo nevkládání základních písem, což může pomoci snížit velikost souboru PDF a zajistit lepší kompatibilitu a konzistentní vzhled dokumentu na různých zařízeních a platformách. Nezapomeňte zvážit důsledky nevložení základních písem a experimentujte, abyste zajistili, že se dokument vykreslí podle očekávání.

### Často kladené otázky

#### Otázka: Jaká je možnost nevkládat základní písma do souboru PDF a proč je to důležité?
Odpověď: Volba nevkládat základní písma do souboru PDF řídí, zda musí být základní písma, jako je Arial, Times New Roman atd., vložena do PDF při převodu dokumentu aplikace Word. To může být důležité pro zmenšení velikosti souboru PDF tím, že se vyhnete zahrnutí písem běžně dostupných v systémech pro čtení PDF. Může také pomoci zajistit lepší kompatibilitu a konzistentní vzhled dokumentu PDF na různých zařízeních a platformách.

#### Otázka: Jak mohu nakonfigurovat Aspose.Words pro .NET, aby do souboru PDF nevkládala základní písma?
Odpověď: Chcete-li nakonfigurovat Aspose.Words pro .NET tak, aby do souboru PDF nevkládala základní písma, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Načtěte dokument Word, který chcete převést do PDF, pomocí`Document` třída a zadaná cesta dokumentu.

 Vytvořte instanci souboru`PdfSaveOptions` třídu a nastavte`UseCoreFonts`majetek do`true`. Vyhnete se tak vkládání základních písem do vygenerovaného souboru PDF.

 Použijte`Save` metoda`Document` objekt k uložení dokumentu ve formátu PDF s uvedením dříve nakonfigurovaných voleb převodu.

#### Otázka: Jaké jsou výhody nevkládání základních písem do souboru PDF?
Odpověď: Výhody nevkládání základních písem do souboru PDF jsou:

Zmenšení velikosti souboru PDF: Tím, že se vyhnete vkládání běžně dostupných písem, jako je Arial, Times New Roman atd., lze zmenšit velikost souboru PDF, což usnadňuje ukládání, sdílení a přenos souborů.

Lepší kompatibilita: Použitím základních písem běžně dostupných v systémech pro čtení PDF zajistíte lepší kompatibilitu a vzhled dokumentu na různých zařízeních a platformách.

#### Otázka: Jaké jsou důsledky nevložení základních písem do souboru PDF?
Odpověď: Důsledky nevložení základních písem do souboru PDF jsou následující:

Odlišný vzhled: Pokud základní písma nejsou k dispozici v systému, kde je soubor PDF otevřen, použijí se náhradní písma, což může mít za následek jiný vzhled, než je zamýšleno.

Problémy s čitelností: Použité náhradní písma nemusí být tak čitelné jako původní písma, což může ovlivnit čitelnost dokumentu.