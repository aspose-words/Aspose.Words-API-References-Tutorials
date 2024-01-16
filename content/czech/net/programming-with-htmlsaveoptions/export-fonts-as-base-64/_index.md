---
title: Exportovat písma jako základ 64
linktitle: Exportovat písma jako základ 64
second_title: Aspose.Words API pro zpracování dokumentů
description: Krok za krokem průvodce exportem základních 64 písem při ukládání dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro export základních 64 písem pomocí Aspose.Words pro .NET. Tato funkce umožňuje exportovat písma jako základní 64 data při ukládání dokumentu ve formátu HTML.

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

Nyní nakonfigurujeme možnosti uložení HTML pro export základních 64 písem. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Tento kód vytvoří instanci`HtmlSaveOptions` a sady`ExportFontsAsBase64` na`true` určit, že písma by měla být exportována jako základní 64 data při ukládání jako HTML.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve nakonfigurovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Tento kód převede dokument do HTML a uloží jej do souboru s fonty exportovanými jako data base 64.

### Příklad zdrojového kódu pro Export Fonts As Base 64 pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů v`dataDir` variabilní.

Nyní jste se naučili, jak exportovat základní 64 písem při ukládání dokumentu jako HTML pomocí Aspose.Words for .NET. Podle podrobného průvodce uvedeného v tomto kurzu můžete snadno exportovat písma bezpečně a vložená do dokumentů HTML.