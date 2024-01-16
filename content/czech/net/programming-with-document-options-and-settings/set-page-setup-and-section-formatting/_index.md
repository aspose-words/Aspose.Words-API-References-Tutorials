---
title: Nastavte Vzhled stránky a Formátování oddílů
linktitle: Nastavte Vzhled stránky a Formátování oddílů
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením rozvržení dokumentu a formátování oddílů pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro nastavení rozložení a formátování sekcí pomocí Aspose.Words pro .NET. Tato funkce umožňuje nastavit orientaci stránky, okraje a velikost papíru.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu

V tomto kroku vytvoříme nový dokument. K vytvoření dokumentu a inicializaci konstruktoru použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kam chcete dokument uložit.

## Krok 3: Nastavení rozvržení a uložení dokumentu

Nyní nakonfigurujeme rozvržení dokumentu. K nastavení orientace, okrajů a velikosti papíru použijte následující kód:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Tento kód nastaví orientaci stránky na šířku, levý okraj na 50 a velikost papíru na 10x14.

### Příklad zdrojového kódu pro nastavení nastavení stránky a formátování oddílů pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Nezapomeňte zadat správnou cestu k adresáři, do kterého chcete dokument uložit`dataDir` variabilní.

Nyní jste se naučili, jak nakonfigurovat rozvržení a formátování oddílů dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce uvedeného v tomto tutoriálu můžete snadno přizpůsobit rozvržení a formátování svých vlastních dokumentů.