---
title: Více sekce
linktitle: Více sekce
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak načíst a zpracovat vícedílné strukturované tagy dokumentu v dokumentu Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/multi-section/
---

Tento tutoriál vysvětluje, jak pracovat s víceoddílovými strukturovanými značkami dokumentu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Můžete načíst a zpracovat značky sekcí přítomné v dokumentu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vložte dokument a načtěte štítky s více sekcemi
 Načtěte dokument aplikace Word pomocí`Document` konstruktor, předá cestu k dokumentu jako parametr. Získejte všechny počáteční uzly rozsahu tagů strukturovaného dokumentu v dokumentu pomocí`GetChildNodes` metoda.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Krok 3: Zpracujte štítky s více sekcemi
Procházejte kolekci počátečních uzlů rozsahu značek strukturovaného dokumentu. V tomto příkladu jednoduše vytiskneme název každé značky do konzole. Další zpracování můžete provádět na základě vašich požadavků.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Příklad zdrojového kódu pro Multi Section pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

A je to! Úspěšně jste načetli a zpracovali víceoddílové strukturované tagy dokumentu ve vašem dokumentu Word pomocí Aspose.Words for .NET.