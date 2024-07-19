---
title: Export zdrojů
linktitle: Export zdrojů
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce pro export zdrojů dokumentu při ukládání jako HTML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/export-resources/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro export zdrojů dokumentů pomocí Aspose.Words pro .NET. Tato funkce umožňuje exportovat zdroje, jako jsou písma, jako externí soubory při ukládání dokumentu ve formátu HTML.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument k exportu. K načtení dokumentu ze zadaného adresáře použijte následující kód:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Tento kód vytvoří instanci`Document` načtením dokumentu ze zadaného adresáře.

## Krok 3: Konfigurace možností zálohování HTML

Nyní nakonfigurujeme možnosti uložení HTML pro export zdrojů dokumentu. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 Tento kód vytvoří instanci`HtmlSaveOptions` a nastaví následující možnosti:

- `CssStyleSheetType` je nastaveno na`CssStyleSheetType.External` pro export šablony stylů CSS do externího souboru.
- `ExportFontResources` je nastaveno na`true` pro export zdrojů písem.
- `ResourceFolder` určuje cílový adresář, kam budou prostředky uloženy.
- `ResourceFolderAlias`určuje alias URL, který bude použit pro přístup ke zdrojům.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve nakonfigurovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Tento kód převede dokument do HTML a uloží prostředky do určeného adresáře pomocí zadaného aliasu URL.

### Příklad zdrojového kódu pro export zdrojů pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů v`dataDir` variabilní.