---
title: Rozbalte Formátování na buňky a řádek ze stylu
linktitle: Rozbalte Formátování na buňky a řádek ze stylu
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce rozšířením formátování na buňky a řádky ze stylu tabulky pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

V tomto tutoriálu vás provedeme krok za krokem procesem rozšíření formátování na buňky a řádky ze stylu pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak použít formátování stylu tabulky na konkrétní buňky a řádky v dokumentech aplikace Word pomocí Aspose.Words for .NET.


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

## Krok 3: Přejděte do první buňky první tabulky
 Chcete-li začít, musíme přejít do první buňky první tabulky v dokumentu. Používáme`GetChild()` a`FirstRow.FirstCell` metody pro získání odkazu na první buňku.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Krok 4: Zobrazit počáteční formátování buňky
Před Rozbalením stylů tabulky zobrazíme aktuální barvu pozadí buňky. Toto by mělo být prázdné, protože aktuální formátování je uloženo ve stylu tabulky.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Krok 5: Rozbalte Styly tabulek na Přímé formátování
 Nyní rozšíříme styly tabulek na přímé formátování pomocí dokumentu`ExpandTableStylesToDirectFormatting()` metoda.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Krok 6: Zobrazte formátování buněk po rozšíření stylu
Nyní zobrazíme barvu pozadí buňky po rozbalení stylů tabulky. Ze stylu tabulky by měla být použita modrá barva pozadí.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Ukázkový zdrojový kód pro rozšíření formátování na buňky a řádky ze stylu pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Získejte první buňku první tabulky v dokumentu.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Nejprve vytiskněte barvu stínování buňky.
	// Toto by mělo být prázdné, protože aktuální stínování je uloženo ve stylu tabulky.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Nyní vytiskněte stínování buněk po rozbalení stylů tabulky.
	// Ze stylu tabulky by měla být použita modrá barva pozadí.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Závěr
tomto tutoriálu jsme se naučili, jak rozšířit formátování na buňky a řádky ze stylu tabulky pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno použít formátování stylu tabulky na konkrétní buňky a řádky v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete dále upravovat rozvržení a prezentaci dokumentů aplikace Word.