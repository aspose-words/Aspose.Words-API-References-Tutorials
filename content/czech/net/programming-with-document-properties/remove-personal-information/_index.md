---
title: Odebrat osobní údaje
linktitle: Odebrat osobní údaje
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce odstraněním osobních údajů z dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/remove-personal-information/
---

tomto tutoriálu vás provedeme zdrojovým kódem C# k odstranění osobních informací z dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje z dokumentu odstranit citlivé osobní informace, jako jsou identifikační údaje autora.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku nahrajeme dokument aplikace Word, ze kterého chceme odstranit osobní údaje. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Smažte osobní údaje

 Nyní umožníme odstranění osobních údajů nastavením`RemovePersonalInformation`majetek do`true`. Použijte následující kód:

```csharp
doc.RemovePersonalInformation = true;
```

Tento kód aktivuje vymazání osobních údajů v dokumentu.

## Krok 4: Uložení dokumentu

Nakonec dokument uložíme s odstraněnými osobními údaji. Použijte následující kód:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Tento kód uloží dokument s odstraněnými osobními informacemi do nového souboru.

### Příklad zdrojového kódu pro Remove Personal Information using Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak odstranit osobní informace z dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce uvedeného v tomto kurzu můžete snadno odstranit citlivé informace ze svých vlastních dokumentů.