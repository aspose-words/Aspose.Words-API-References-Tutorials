---
title: Převést metasoubory na EMF nebo WMF
linktitle: Převést metasoubory na EMF nebo WMF
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce převodem metasouborů do formátu EMF nebo WMF při převodu dokumentu do HTML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

tomto tutoriálu vás provedeme zdrojovým kódem C# pro převod metasouborů do formátu EMF nebo WMF pomocí Aspose.Words for .NET. Tato funkce umožňuje při převodu dokumentu do HTML převádět obrázky ve formátu metasouboru do kompatibilních formátů, jako je EMF nebo WMF.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Vložení obrázku do dokumentu

V tomto kroku vložíme do dokumentu, který má být převeden, obrázek. Chcete-li vložit obrázek ze zdroje dat pomocí značky HTML, použijte následující kód:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Tento kód vytvoří instanci`Document` a`DocumentBuilder` k vytvoření dokumentu. Vkládá an`<img>` tag do dokumentu se zakódovaným obrázkem base64.

## Krok 3: Nastavte možnosti uložení HTML

Nyní nastavíme možnosti uložení HTML, včetně formátu metasouboru pro obrázky. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Tento kód vytvoří instanci`HtmlSaveOptions` a sady`MetafileFormat` na`HtmlMetafileFormat.EmfOrWmf` určit, že metasoubory mají být při převodu do HTML převedeny do formátu EMF nebo WMF.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve definovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Tento kód převede dokument do HTML a uloží jej do souboru s převedenými metasoubory ve formátu EMF nebo WMF v závislosti na nastavených možnostech uložení.

### Příklad zdrojového kódu pro Převést metasoubory do EMF nebo WMF pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů v`dataDir` variabilní.

Nyní jste se naučili, jak převést metasoubory do formátu EMF nebo WMF při převodu dokumentu do HTML pomocí Aspose.Words for .NET. Podle podrobného průvodce poskytnutého v tomto kurzu můžete snadno spravovat metasoubory v převedených dokumentech HTML.