---
title: Vyřešte názvy písem
linktitle: Vyřešte názvy písem
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce řešením chybějících názvů písem při převodu do HTML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/resolve-font-names/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# k vyřešení chybějících názvů písem pomocí Aspose.Words for .NET. Tato funkce umožňuje automaticky vyřešit chybějící názvy písem při převodu dokumentu do HTML.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument ke zpracování. K načtení dokumentu ze zadaného adresáře použijte následující kód:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Tento kód vytvoří instanci`Document` načtením dokumentu ze zadaného adresáře.

## Krok 3: Konfigurace možností zálohování HTML

Nyní nakonfigurujeme možnosti uložení HTML pro vyřešení chybějících názvů písem během převodu. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Tento kód vytvoří instanci`HtmlSaveOptions` a nastaví`ResolveFontNames` možnost`true` vyřešení chybějících názvů písem při převodu do HTML. Také`PrettyFormat` možnost je nastavena na`true` získat pěkně naformátovaný HTML kód.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve nakonfigurovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Tento kód převede dokument na HTML automatickým vyřešením chybějících názvů písem a uloží převedený soubor HTML do určeného adresáře.

### Příklad zdrojového kódu pro Resolve Font Names using Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů v`dataDir` variabilní.