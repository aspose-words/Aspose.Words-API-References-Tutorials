---
title: Přidat uživatelské vlastnosti dokumentu
linktitle: Přidat uživatelské vlastnosti dokumentu
second_title: Aspose.Words API pro zpracování dokumentů
description: Krok za krokem průvodce přidáním vlastních vlastností do dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/add-custom-document-properties/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro přidání uživatelských vlastností do dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje přidat do dokumentu vlastní informace.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument Wordu, do kterého chceme přidat uživatelské vlastnosti. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Přidejte vlastní vlastnosti

Nyní do dokumentu přidáme uživatelské vlastnosti. Chcete-li přidat vlastnosti, použijte následující kód:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Tento kód nejprve zkontroluje, zda v uživatelských vlastnostech již existuje vlastnost "Authorized". Pokud existuje, proces se přeruší. V opačném případě budou uživatelské vlastnosti přidány do dokumentu.

### Příklad zdrojového kódu pro Add Custom Document Properties pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak přidat uživatelské vlastnosti do dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce poskytnutého v tomto kurzu můžete do dokumentů snadno přidat vlastní uživatelské vlastnosti.