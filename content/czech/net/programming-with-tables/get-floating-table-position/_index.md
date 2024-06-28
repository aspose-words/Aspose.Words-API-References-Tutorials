---
title: Získejte pozici plovoucího stolu
linktitle: Získejte pozici plovoucího stolu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak získat pozici plovoucích tabulek v dokumentu aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/get-floating-table-position/
---

V tomto tutoriálu se naučíme, jak získat pozici plovoucí tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově získat vlastnosti umístění plovoucí tabulky v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu a přístup k tabulkám
Chcete-li spustit textový procesor s tabulkami, musíme načíst dokument, který je obsahuje, a získat k nim přístup. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů. Také se ujistěte, že dokument obsahuje plovoucí tabulky.

## Krok 3: Získání vlastností umístění plovoucího stolu
Dále projdeme všechny tabulky v dokumentu a získáme vlastnosti umístění plovoucí tabulky. Použijte následující kód:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Pokud je pole plovoucího typu, vytiskněte jeho vlastnosti umístění.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Zde používáme a`foreach` smyčka pro procházení všech polí v dokumentu. Zkontrolujeme, zda je pole typu float zaškrtnutím`TextWrapping` vlastnictví. Pokud ano, vytiskneme vlastnosti umístění tabulky, jako je horizontální kotva, vertikální kotva, absolutní horizontální a vertikální vzdálenosti, povolení překrytí, absolutní horizontální vzdálenost a relativní vertikální zarovnání.
 
### Ukázkový zdrojový kód pro Get Floating Table Position pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Pokud je tabulka plovoucího typu, vytiskněte její vlastnosti umístění.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Závěr
tomto tutoriálu jsme se naučili, jak získat pozici plovoucí tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete programově získat vlastnosti umístění plovoucích tabulek v dokumentech aplikace Word. Tato funkce vám umožňuje analyzovat a manipulovat s plovoucími tabulkami podle vašich specifických potřeb.