---
title: Zobrazit možnosti
linktitle: Zobrazit možnosti
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce konfigurací možností zobrazení dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-options-and-settings/view-options/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro konfiguraci možností zobrazení pomocí Aspose.Words pro .NET. Tato funkce umožňuje přizpůsobit režim zobrazení a úroveň přiblížení v dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument aplikace Word, pro který chceme konfigurovat možnosti zobrazení. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Konfigurace možností zobrazení

Nyní nakonfigurujeme možnosti zobrazení dokumentu. Pomocí následujícího kódu nastavte režim zobrazení a úroveň přiblížení:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Tento kód nastaví režim zobrazení na „PageLayout“ a úroveň přiblížení na 50 %.

### Příklad zdrojového kódu pro Možnosti zobrazení pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak konfigurovat možnosti zobrazení dokumentu pomocí Aspose.Words pro .NET. Podle podrobného průvodce uvedeného v tomto kurzu si můžete snadno přizpůsobit zobrazení svých vlastních dokumentů.