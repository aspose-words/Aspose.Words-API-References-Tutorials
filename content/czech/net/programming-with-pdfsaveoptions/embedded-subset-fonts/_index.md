---
title: Vložení podmnožin písem do dokumentu PDF
linktitle: Vložení podmnožin písem do dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce vkládáním podmnožin písem do dokumentu PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Tento článek obsahuje podrobného průvodce, jak používat funkci vkládání podmnožiny písem s Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak vložit podmnožiny písem do dokumentu a vygenerovat PDF obsahující pouze glyfy použité v dokumentu.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Chcete-li začít, musíte definovat cestu k adresáři, kde jsou umístěny vaše dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Nahrajte dokument

Dále musíme načíst dokument, který chceme zpracovat. V tomto příkladu předpokládáme, že dokument se nazývá "Rendering.docx" a je umístěn v určeném adresáři dokumentů.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Nakonfigurujte možnosti uložení jako PDF

 Chcete-li vytvořit PDF obsahující pouze podmnožiny písem použitých v dokumentu, musíme nakonfigurovat`PdfSaveOptions` objekt s`EmbedFullFonts` vlastnost nastavena na`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Krok 4: Uložte dokument jako PDF s podmnožinami písem

 Nakonec můžeme dokument uložit jako PDF pomocí podmnožin písem. Zadejte název výstupního souboru a`saveOptions` objekt, který jsme nakonfigurovali v předchozím kroku.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

To je vše ! Úspěšně jste vložili podmnožiny písem do dokumentu a pomocí Aspose.Words for .NET vygenerovali PDF obsahující pouze glyfy použité v dokumentu.

### Ukázka zdrojového kódu pro vkládání podmnožin písem pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Výstupní PDF bude obsahovat podmnožiny písem v dokumentu.
	// Do písem PDF jsou zahrnuty pouze glyfy použité v dokumentu.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Závěr

V tomto tutoriálu jsme se naučili, jak vložit podmnožiny písem do dokumentu PDF pomocí Aspose.Words for .NET. Vkládání podmnožin písem pomáhá zmenšit velikost souboru PDF při zachování vzhledu dokumentu použitím pouze skutečně použitých znaků. To zajišťuje lepší kompatibilitu a výkon při prohlížení a tisku PDF. Neváhejte dále prozkoumat funkce Aspose.Words pro .NET, abyste optimalizovali generování vašich dokumentů PDF s vloženými podmnožinami písem.

### Často kladené otázky

#### Otázka: Co je vkládání podmnožin písem do dokumentu PDF?
Odpověď: Vložení podmnožin písem do dokumentu PDF je proces, kdy se zahrnou pouze glyfy použité v dokumentu, nikoli všechna kompletní písma. Tím se zmenšuje velikost souboru PDF tím, že obsahuje pouze data písma nezbytná k zobrazení znaků skutečně použitých v dokumentu.

#### Otázka: Jaký je rozdíl mezi vkládáním celých písem a vkládáním podmnožin písem?
Odpověď: Úplné vložení písem znamená zahrnutí všech písem použitých v dokumentu do souboru PDF, což zajišťuje, že dokument bude zobrazen přesně tak, jak byl navržen, ale může zvětšit velikost souboru PDF. Naproti tomu vkládání podmnožin písem obsahuje pouze glyfy použité v dokumentu, čímž se zmenšuje velikost souboru PDF, ale omezuje se možnost přesně replikovat vzhled dokumentu, pokud se později přidají další znaky.

#### Otázka: Jak mohu vložit podmnožiny písem do dokumentu PDF pomocí Aspose.Words for .NET?
Odpověď: Chcete-li vložit podmnožiny písem do dokumentu PDF pomocí Aspose.Words pro .NET, postupujte takto:

 Nastavte cestu k adresáři dokumentu nahrazením`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Vložte dokument, který chcete zpracovat, pomocí`Document` třída a cesta dokumentu.

 Nakonfigurujte možnosti uložení PDF vytvořením instance souboru`PdfSaveOptions` třídy a nastavení`EmbedFullFonts`majetek do`false`Tím zajistíte, že do souboru PDF budou zahrnuty pouze podmnožiny písem použité v dokumentu.

 Uložte dokument ve formátu PDF s vloženými podmnožinami písem pomocí`Save` metoda`Document` objekt s uvedením názvu výstupního souboru a dříve nakonfigurovaných voleb uložení.

#### Otázka: Jaké jsou výhody vkládání podmnožin písem do dokumentu PDF?
Odpověď: Výhody vkládání podmnožin písem do dokumentu PDF jsou:

Zmenšená velikost souboru PDF: Zahrnutím pouze glyfů použitých v dokumentu se velikost souboru PDF zmenší ve srovnání s vložením plných písem.

Zachování vzhledu dokumentu: Podmnožiny písem obsažené v souboru PDF umožňují reprodukovat vzhled dokumentu pouze pomocí skutečně použitých znaků.

Kompatibilita s omezeními licence: Vkládání podmnožin písem může být preferováno v případech, kdy plná písma nelze legálně vložit z důvodu licenčních omezení.