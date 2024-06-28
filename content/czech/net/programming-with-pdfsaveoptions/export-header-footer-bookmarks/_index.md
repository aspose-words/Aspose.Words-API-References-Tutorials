---
title: Exportujte záložky Záhlaví dokumentu Word do dokumentu PDF
linktitle: Exportujte záložky Záhlaví dokumentu Word do dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem pro export záložek záhlaví zápatí dokumentu do záložek dokumentu PDF pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Tento článek poskytuje podrobného průvodce, jak exportovat záložky záhlaví zápatí dokumentu aplikace Word do funkce dokumentu PDF pomocí Aspose.Words for .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak exportovat záložky ze záhlaví a zápatí dokumentu a vygenerovat PDF s příslušnými záložkami.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Chcete-li začít, musíte definovat cestu k adresáři, kde jsou umístěny vaše dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Nahrajte dokument

Dále musíme načíst dokument, který chceme zpracovat. V tomto příkladu předpokládáme, že dokument se nazývá "Záložky v záhlaví a zápatí.docx" a je umístěn v určeném adresáři dokumentů.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Krok 3: Nakonfigurujte možnosti uložení jako PDF

 Chcete-li exportovat záložky záhlaví a zápatí, musíme nakonfigurovat`PdfSaveOptions` objekt. V tomto příkladu nastavíme výchozí úroveň obrysu záložek na 1 a režim exportu záložek záhlaví a zápatí na „První“.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Krok 4: Uložte dokument jako PDF se záložkami záhlaví a zápatí

Nakonec můžeme dokument uložit ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

To je vše ! Úspěšně jste exportovali záložky záhlaví a zápatí z dokumentu a vygenerovali PDF s příslušnými záložkami pomocí Aspose.Words for .NET.

### Ukázkový zdrojový kód pro export záložek záhlaví a zápatí pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Závěr

tomto tutoriálu jsme vysvětlili, jak exportovat záložky záhlaví a zápatí z dokumentu aplikace Word do dokumentu PDF pomocí Aspose.Words for .NET. Exportované záložky umožňují snadnou navigaci a rychlý odkaz na odpovídající záhlaví a zápatí ve vygenerovaném dokumentu PDF. Podle popsaných kroků exportujte záložky záhlaví a zápatí z dokumentu a vygenerujte PDF s příslušnými záložkami pomocí Aspose.Words for .NET. Ujistěte se, že jste zadali správnou cestu ke svým dokumentům a podle potřeby nakonfigurujte možnosti uložení.

### Často kladené otázky

### Otázka: Co je export záložek záhlaví a zápatí z dokumentu aplikace Word do dokumentu PDF?
Odpověď: Export záložek záhlaví a zápatí z dokumentu aplikace Word do dokumentu PDF je funkce pro uchování a generování záložek v dokumentu PDF ze záhlaví a zápatí. zápatí původního dokumentu aplikace Word. To umožňuje uživatelům rychle a snadno procházet dokumentem PDF pomocí záložek odpovídajících záhlaví a zápatí.

### Otázka: Jak mohu pomocí Aspose.Words for .NET exportovat záložky záhlaví a zápatí z dokumentu aplikace Word do dokumentu PDF?
A: Chcete-li exportovat záložky záhlaví a zápatí z dokumentu aplikace Word do dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Vložte dokument, který chcete zpracovat, pomocí`Document` třídy a zadejte cestu k dokumentu aplikace Word v zadaném adresáři dokumentů.

 Nakonfigurujte možnosti uložení jako PDF vytvořením instance souboru`PdfSaveOptions` třídy a nastavení příslušných možností záložky záhlaví a zápatí.

 Uložte dokument ve formátu PDF pomocí`Save` metoda`Document` třída určující cestu a možnosti uložení.

### Otázka: Jaké jsou výhody exportu záložek záhlaví a zápatí do dokumentu PDF?
A: Výhody exportu záložek záhlaví a zápatí do dokumentu PDF jsou:

Snadná navigace: Záložky umožňují uživatelům snadno se pohybovat v dokumentu PDF odkazem na konkrétní záhlaví a zápatí.

Rychlý průvodce: Záložky umožňují uživatelům rychle najít relevantní části dokumentu PDF na základě záhlaví a zápatí.