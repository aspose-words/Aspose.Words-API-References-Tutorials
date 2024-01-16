---
title: Konfigurace odkazu na obsah
linktitle: Konfigurace odkazu na obsah
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením propojení s obsahem v dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/configuring-link-to-content/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# pro nastavení propojení s obsahem pomocí Aspose.Words for .NET. Tato funkce umožňuje odkazovat na konkrétní obsah v dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Vytvoření dokumentu a konstruktoru

V tomto kroku vytvoříme nový dokument a inicializujeme konstruktor. Použijte následující kód:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vytvořte záložku

Nyní vytvoříme záložku v dokumentu. K vytvoření záložky s textem použijte následující kód:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Tento kód vytvoří záložku s názvem „MyBookmark“ a přidá do ní nějaký text.

## Krok 4: Nastavení odkazu na obsah

Nyní nakonfigurujeme odkaz na obsah pomocí vlastností dokumentu. Pomocí následujícího kódu přidejte a načtěte odkaz na obsah:

```csharp
// Získejte seznam všech uživatelských vlastností v dokumentu.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Přidejte vlastnost vázanou na obsah.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Tento kód přidá vlastnost související s obsahem nazvanou „Záložka“ se záložkou „MyBookmark“. Poté načte informace o vlastnostech souvisejících s obsahem, jako je stav odkazu, zdroj odkazu a hodnota vlastnosti.

### Příklad zdrojového kódu pro konfiguraci odkazu na obsah pomocí Aspose.Words pro .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Načtěte seznam všech uživatelských vlastností dokumentu ze souboru.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Přidat propojené s vlastností obsahu.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Nyní jste se naučili, jak nakonfigurovat odkaz na obsah v dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce poskytnutého v tomto kurzu můžete snadno vytvářet a konfigurovat odkazy na konkrétní obsah ve vašich vlastních dokumentech.