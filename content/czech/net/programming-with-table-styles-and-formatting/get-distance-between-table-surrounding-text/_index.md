---
title: Získejte vzdálenost mezi textem obklopujícím tabulku
linktitle: Získejte vzdálenost mezi textem obklopujícím tabulku
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce k získání vzdálenosti mezi textem a tabulkou v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

tomto tutoriálu vás provedeme krok za krokem procesem získání vzdálenosti mezi okolním textem v tabulce pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak získat přístup k různým vzdálenostem mezi tabulkou a okolním textem v dokumentech aplikace Word pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Zde se nachází váš dokument aplikace Word. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte existující dokument
 Dále musíte načíst existující dokument aplikace Word do instance souboru`Document` třída.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Krok 3: Získejte vzdálenost mezi tabulkou a okolním textem
 Abychom získali vzdálenost mezi tabulkou a okolním textem, musíme k tabulce v dokumentu přistupovat pomocí`GetChild()` metoda a`NodeType.Table` vlastnictví. Potom můžeme zobrazit různé vzdálenosti pomocí vlastností pole`DistanceTop`, `DistanceBottom`, `DistanceRight`a`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Ukázkový zdrojový kód pro Get Distance Between Table Surrounding Text pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Závěr
tomto tutoriálu jsme se naučili, jak získat vzdálenost mezi okolním textem v tabulce pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno získat přístup k různým vzdálenostem mezi tabulkou a okolním textem v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete analyzovat rozložení vašich tabulek ve vztahu k textu a vyhovět specifickým potřebám.