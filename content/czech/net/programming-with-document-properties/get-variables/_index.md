---
title: Získejte proměnné
linktitle: Získejte proměnné
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce pro načtení proměnných dokumentu pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-document-properties/get-variables/
---

V tomto tutoriálu vás provedeme zdrojovým kódem C# k načtení proměnných z dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje přístup k proměnným definovaným v dokumentu.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt C# ve svém oblíbeném IDE. Ujistěte se, že váš projekt odkazuje na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu

V tomto kroku načteme dokument Wordu, ze kterého chceme proměnné načíst. K načtení dokumentu použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

## Krok 3: Načtení proměnných

Nyní načteme proměnné definované v dokumentu. Použijte následující kód:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Tento kód iteruje každý pár klíč–hodnota v proměnných dokumentu a získá název a hodnotu každé proměnné. Proměnné jsou poté zřetězeny, aby se zobrazily informace pro každou proměnnou.

### Příklad zdrojového kódu pro Get Variables pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Ujistěte se, že jste zadali správnou cestu dokumentu v`dataDir` variabilní.

Nyní jste se naučili, jak načíst proměnné z dokumentu pomocí Aspose.Words for .NET. Podle podrobného průvodce v tomto kurzu můžete snadno přistupovat a zobrazovat proměnné z vašich vlastních dokumentů.