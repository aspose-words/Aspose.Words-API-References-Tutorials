---
title: Převést metasoubory na svg
linktitle: Převést metasoubory na svg
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce převodem metasouborů do formátu SVG při převodu dokumentu do HTML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro převod metasouborů do formátu SVG pomocí Aspose.Words for .NET. Tato funkce umožňuje převést metasoubory do formátu SVG při převodu dokumentu do HTML.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Vložení obrázku SVG do dokumentu

V tomto kroku vložíme do dokumentu, který má být převeden, obrázek SVG. Chcete-li vložit obrázek SVG pomocí značky HTML, použijte následující kód:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Tento kód vytvoří instanci`Document`a`DocumentBuilder` k vytvoření dokumentu. Vkládá a`<svg>` značka obsahující a`<polygon>` prvek s atributy pro definování tvaru a stylu obrázku SVG.

## Krok 3: Nastavte možnosti uložení HTML

Nyní nastavíme možnosti uložení HTML a určíme, že metasoubory mají být převedeny do formátu SVG. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Tento kód vytvoří instanci`HtmlSaveOptions` a sady`MetafileFormat` na`HtmlMetafileFormat.Svg` určit, že metasoubory mají být při převodu do HTML převedeny do formátu SVG.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve definovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Tento kód převede dokument do HTML a uloží jej do souboru s metasoubory převedenými na SVG.

### Příklad zdrojového kódu pro Convert Metafiles To Svg pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
