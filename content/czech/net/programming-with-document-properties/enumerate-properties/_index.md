---
title: Výčet vlastností
linktitle: Výčet vlastností
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce výčtem vlastností dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/enumerate-properties/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro výčet vlastností dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje přístup k vestavěným a uživatelským vlastnostem dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument Wordu, jehož vlastnosti chceme vypsat. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Výčet vlastností

Nyní si vyjmenujme vlastnosti dokumentu, a to jak vestavěné, tak uživatelské vlastnosti. Použijte následující kód:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Tento kód zobrazí název dokumentu a poté vypíše vestavěné a uživatelské vlastnosti s jejich názvem a hodnotou.

### Příklad zdrojového kódu pro Enumerate Properties pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak vytvořit výčet vlastností dokumentu pomocí Aspose.Words pro .NET. Podle podrobného průvodce uvedeného v tomto kurzu můžete snadno přistupovat a zobrazovat vlastnosti svých vlastních dokumentů.

