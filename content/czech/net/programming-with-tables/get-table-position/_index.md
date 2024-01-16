---
title: Získejte pozici stolu
linktitle: Získejte pozici stolu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak získat pozici tabulky v dokumentu Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/get-table-position/
---

V tomto tutoriálu se naučíme, jak získat pozici tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci programově získat vlastnosti umístění tabulky v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu a přístup k tabulce
Abychom mohli textový procesor spustit s tabulkou, musíme načíst dokument, který ji obsahuje, a získat k němu přístup. Následuj tyto kroky:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Tables.docx");

// Přístup k poli
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů. Také se ujistěte, že dokument obsahuje tabulku, jejíž pozici chcete získat.

## Krok 3: Získání vlastností umístění pole
Dále zkontrolujeme typ umístění pole a získáme příslušné vlastnosti umístění. Použijte následující kód:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Zde používáme podmínku ke kontrole, zda je pole typu float. Pokud ano, vytiskneme`RelativeHorizontalAlignment` a`RelativeVerticalAlignment` vlastnosti, abyste získali relativní horizontální a vertikální zarovnání tabulky. V opačném případě vytiskneme`Alignment` vlastnost pro získání zarovnání pole.

### Ukázkový zdrojový kód pro Get Table Position pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Závěr
tomto tutoriálu jsme se naučili, jak získat pozici tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete získat vlastnosti umístění tabulky v dokumentech aplikace Word programově. Tato funkce vám umožňuje analyzovat a manipulovat s poli podle jejich specifických pozic.