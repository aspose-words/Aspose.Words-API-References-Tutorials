---
title: Použít ohraničení obrysu
linktitle: Použít ohraničení obrysu
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce aplikací ohraničení obrysu na tabulku pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

tomto tutoriálu vás provedeme krok za krokem procesem použití obrysového ohraničení na tabulku pomocí Aspose.Words for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete mít jasno v tom, jak manipulovat s ohraničením tabulek v dokumentech aplikace Word pomocí Aspose.Words for .NET.

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Zde je uložen váš dokument aplikace Word. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Nahrajte dokument
 Dále musíte načíst dokument aplikace Word do instance souboru`Document` třída.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Krok 3: Přístup k tabulce
 Chcete-li použít ohraničení obrysu, potřebujeme získat přístup k tabulce v dokumentu. The`Table` class představuje tabulku v Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Krok 4: Zarovnejte tabulku na střed stránky
 Nyní můžeme tabulku zarovnat na střed stránky pomocí`Alignment` vlastnost stolu.

```csharp
table. Alignment = Table Alignment. Center;
```

## Krok 5: Vymažte existující okraje tabulky.
Chcete-li začít s novým ohraničením obrysu, musíme nejprve vymazat všechna existující ohraničení z tabulky. To lze provést pomocí`ClearBorders()` metoda.

```csharp
table. ClearBorders();
```

## Krok 6: Definujte zelený okraj kolem stolu
 Nyní můžeme nastavit zelený okraj kolem stolu pomocí`SetBorder()` metoda pro každou stranu stolu. V tomto příkladu používáme ohraničení typu „Single“ s tloušťkou 1,5 bodu a zelenou barvou.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Krok 7: Vyplňte buňky barvou pozadí.
Pro zlepšení vizuální prezentace tabulky můžeme buňky vyplnit základní barvou pozadí.

idea. V tomto příkladu používáme světle zelenou barvu.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Krok 8: Uložte upravený dokument
Nakonec upravený dokument uložíme do souboru. Můžete zvolit vhodný název a umístění výstupního dokumentu.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

gratuluji! Nyní jste použili ohraničení obrysu na tabulku pomocí Aspose.Words for .NET.

### Ukázkový zdrojový kód pro Apply Outline Border pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Zarovnejte tabulku na střed stránky.
	table.Alignment = TableAlignment.Center;
	//Odstraňte všechna existující ohraničení z tabulky.
	table.ClearBorders();
	// Nastavte zelený okraj kolem stolu, ale ne uvnitř.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Vyplňte buňky světle zelenou plnou barvou.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak aplikovat ohraničení obrysu na tabulku pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce můžete snadno integrovat tuto funkci do svých projektů C#. Manipulace s formátováním tabulek je základním aspektem zpracování dokumentů a Aspose.Words nabízí výkonné a flexibilní API, jak toho dosáhnout. S těmito znalostmi můžete zlepšit vizuální prezentaci vašich dokumentů Word a splnit specifické požadavky.