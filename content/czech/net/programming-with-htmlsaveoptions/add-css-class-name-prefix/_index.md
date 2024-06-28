---
title: Přidat předponu názvu třídy CSS
linktitle: Přidat předponu názvu třídy CSS
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce přidáním předpony názvu třídy CSS při převodu dokumentu do HTML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro přidání předpony názvu třídy CSS pomocí Aspose.Words for .NET. Tato funkce umožňuje přidat vlastní předponu k vygenerovaným názvům tříd CSS při převodu dokumentu do HTML.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument Wordu, který chceme převést do HTML. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Nastavte možnosti uložení HTML

Nyní nastavíme možnosti uložení HTML, včetně typu šablony stylů CSS a předpony názvu třídy CSS. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Tento kód vytvoří instanci`HtmlSaveOptions` a sady`CssStyleSheetType` na`CssStyleSheetType.External`vygenerovat externí šablonu stylů CSS a`CssClassNamePrefix` na`"pfx_"` předponovat`"pfx_"` pojmenovat třídy CSS.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve definovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Tento kód převede dokument do HTML a uloží jej do souboru s přidanou předponou názvu třídy CSS.

### Příklad zdrojového kódu pro Add Css Class Name Prefix pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak přidat předponu názvu třídy CSS při převodu dokumentu do HTML pomocí Aspose.Words for .NET. V návaznosti na krok za krokem průvodce, který je uveden v tomto kurzu, můžete upravit názvy tříd CSS v převedených HTML dokumentech.