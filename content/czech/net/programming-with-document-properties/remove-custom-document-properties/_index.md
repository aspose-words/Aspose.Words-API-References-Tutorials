---
title: Odebrat uživatelské vlastnosti dokumentu
linktitle: Odebrat uživatelské vlastnosti dokumentu
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce odstraněním uživatelských vlastností z dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/remove-custom-document-properties/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# k odstranění uživatelských vlastností z dokumentu pomocí Aspose.Words for .NET. Tato funkce vám umožňuje odstranit konkrétní uživatelskou vlastnost z dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

tomto kroku načteme dokument aplikace Word, ze kterého chceme uživatelské vlastnosti odebrat. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Odstranění vlastních vlastností

Nyní z dokumentu odebereme konkrétní uživatelskou vlastnost. Použijte následující kód:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Tento kód odebere z dokumentu vlastní vlastnost "Authorized Date". "Autorizované datum" můžete nahradit názvem vlastní vlastnosti, kterou chcete odstranit.

### Příklad zdrojového kódu pro Remove Custom Document Properties pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak odstranit uživatelské vlastnosti z dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce poskytnutého v tomto kurzu můžete snadno odebrat uživatelské vlastnosti ze svých vlastních dokumentů.