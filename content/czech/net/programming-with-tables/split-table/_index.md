---
title: Rozdělený stůl
linktitle: Rozdělený stůl
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak rozdělit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/split-table/
---

V tomto tutoriálu se naučíme, jak rozdělit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete moci rozdělit tabulku z určitého řádku v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu
Chcete-li spustit textový editor s dokumentem, postupujte takto:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů a uveďte správný název souboru.

## Krok 3: Rozdělení stolu
Dále rozdělíme tabulku z určitého řádku. Použijte následující kód:

```csharp
// Získejte první tabulku
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Určení řádku, od kterého se má tabulka dělit
Row row = firstTable.Rows[2];

// Vytvořte nový kontejner pro rozdělenou tabulku
Table table = (Table)firstTable.Clone(false);

// Vložte kontejner za původní tabulku
firstTable.ParentNode.InsertAfter(table, firstTable);

// Chcete-li zachovat vzdálenost mezi tabulkami, přidejte odstavec vyrovnávací paměti
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Přesunout řádky z původní tabulky do rozdělené tabulky
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Zde používáme dokument k načtení první tabulky z uzlu dokumentu. Poté určíme řádek, ze kterého chceme tabulku rozdělit, v tomto příkladu je to třetí řádek (index 2). Poté vytvoříme nový kontejner naklonováním původní tabulky a poté ji vložíme za původní tabulku. Přidáme také odstavec vyrovnávací paměti, abychom udrželi vzdálenost mezi dvěma tabulkami. Poté přesouváme řádky z původní tabulky do rozdělené tabulky pomocí cyklu do-while, dokud nedosáhneme zadaného řádku.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme uložit

  dokument upravený pomocí dělené tabulky. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázka zdrojového kódu pro Split Table pomocí Aspose.Words pro .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Tabulku rozdělíme na třetí řádek (včetně).
Row row = firstTable.Rows[2];
// Vytvořte nový kontejner pro rozdělenou tabulku.
Table table = (Table) firstTable.Clone(false);
// Vložte nádobu za originál.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Přidejte odstavec vyrovnávací paměti, abyste zajistili, že tabulky zůstanou oddělené.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Závěr
tomto tutoriálu jsme se naučili, jak rozdělit tabulku v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete snadno rozdělit tabulky z určitého řádku v dokumentech aplikace Word.