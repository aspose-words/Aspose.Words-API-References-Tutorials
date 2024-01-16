---
title: Nastavte odsazení buněk
linktitle: Nastavte odsazení buněk
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením okrajů buněk tabulky pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

V tomto tutoriálu vás provedeme krok za krokem procesem nastavení okrajů buněk tabulky pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak upravit levý, horní, pravý a dolní okraj (mezera) obsahu buněk v tabulkách v dokumentech aplikace Word pomocí Aspose.Words for .NET .

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený dokument aplikace Word. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvořte nový dokument a tvůrce dokumentů
 Dále musíte vytvořit novou instanci souboru`Document` třída a konstruktor dokumentu pro tento dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vytvořte novou tabulku a přidejte buňku
Chcete-li začít vytvářet tabulku, použijeme`StartTable()` metoda konstruktoru dokumentu, pak přidáme buňku do tabulky pomocí`InsertCell()` metoda.

```csharp
builder. StartTable();
builder. InsertCell();
```

## Krok 4: Nastavte okraje buněk
 Nyní můžeme nastavit okraje buněk pomocí`SetPaddings()` metoda`CellFormat` objekt. Okraje jsou definovány v bodech a specifikovány v pořadí vlevo, nahoře, vpravo a dole.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Krok 5: Přidejte obsah do buňky
 Poté můžeme přidat obsah do buňky pomocí nástroje pro tvorbu dokumentů`Writeln()` metoda.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Krok 6: Dokončete tabulku a uložte dokument
 Nakonec dokončíme vytváření tabulky pomocí`EndRow()` metoda a`EndTable()`, poté upravený dokument uložíme do souboru.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Ukázkový zdrojový kód pro Set Cell Padding pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Nastaví velikost mezery (v bodech), která se má přidat k levé/horní/pravé/dolní části obsahu buňky.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak nastavit okraje buňky tabulky pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno upravit okraje buněk a vytvořit mezery vlevo, nahoře, vpravo a dole od obsahu v tabulkách v dokumentech aplikace Word. Aspose.Words nabízí výkonné a flexibilní API pro manipulaci a formátování tabulek ve vašich dokumentech. S těmito znalostmi můžete přizpůsobit formátování tabulek svým konkrétním potřebám.