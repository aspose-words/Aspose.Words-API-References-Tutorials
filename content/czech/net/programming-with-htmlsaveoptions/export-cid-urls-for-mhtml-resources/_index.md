---
title: Export Cid URL pro zdroje Mhtml
linktitle: Export Cid URL pro zdroje Mhtml
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce exportem CID URL zdrojů MHTML při ukládání dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro export CID URL pro zdroje MHTML pomocí Aspose.Words pro .NET. Tato funkce umožňuje exportovat CID URL zdrojů MHTML při ukládání dokumentu ve formátu MHTML.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument k exportu. K načtení dokumentu ze zadaného adresáře použijte následující kód:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Tento kód vytvoří instanci`Document` načtením dokumentu ze zadaného adresáře.

## Krok 3: Konfigurace možností zálohování HTML

Nyní nakonfigurujeme možnosti uložení HTML pro export CID URL zdrojů MHTML. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Tento kód vytvoří instanci`HtmlSaveOptions` s formátem uložení nastaveným na MHTML. Umožňuje také export CID URL zdrojů MHTML nastavením`ExportCidUrlsForMhtmlResources` na`true`.

## Krok 4: Převod a uložení dokumentu do MHTML

Nakonec převedeme dokument do MHTML pomocí dříve nakonfigurovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Tento kód převede dokument na MHTML a uloží jej do souboru s adresami URL CID exportovaných zdrojů MHTML.

### Příklad zdrojového kódu pro Export Cid Urls For Mhtml Resources pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů v`dataDir` variabilní.

Nyní jste se naučili, jak exportovat CID URL zdrojů MHTML při ukládání dokumentu ve formátu MHTML pomocí Aspose.Words for .NET. Podle podrobného průvodce uvedeného v tomto kurzu můžete snadno spravovat adresy URL CID v exportovaných dokumentech MHTML.

