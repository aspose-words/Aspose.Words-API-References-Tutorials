---
title: Export zpátečních informací
linktitle: Export zpátečních informací
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce exportem zpátečních informací při ukládání dokumentu jako HTML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

V tomto tutoriálu vás provedeme zdrojovým kódem jazyka C# pro export informací z dokumentu s Aspose.Words for .NET. Tato funkce umožňuje zahrnout do exportovaného souboru HTML informace zpáteční cesty, což usnadňuje načítání změn provedených v původním dokumentu.

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

Nyní nakonfigurujeme možnosti uložení HTML pro export informací o zpětné cestě dokumentu. Použijte následující kód:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Tento kód vytvoří instanci`HtmlSaveOptions` a nastaví`ExportRoundtripInformation` možnost`true` k zahrnutí informací o zpáteční cestě při exportu.

## Krok 4: Převod a uložení dokumentu do HTML

Nakonec převedeme dokument do HTML pomocí dříve nakonfigurovaných možností uložení HTML. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Tento kód převede dokument do HTML včetně informací o zpáteční cestě a uloží exportovaný soubor HTML do určeného adresáře.

### Příklad zdrojového kódu pro Export Roundtrip Information pomocí Aspose.Words for .NET


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů v`dataDir` variabilní.