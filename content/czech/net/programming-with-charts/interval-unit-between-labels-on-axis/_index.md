---
title: Interval Jednotka Mezi štítky Na ose Grafu
linktitle: Interval Jednotka Mezi štítky Na ose Grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit jednotku intervalu mezi štítky na ose grafu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k nastavení jednotky intervalu mezi štítky na ose grafu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a přizpůsobit popisky os.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

- Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout pomocí správce balíčků NuGet k instalaci.
- Cesta k adresáři dokumentu, kam bude výstupní dokument uložen.

## Krok 2: Vytvořte nový dokument a vložte graf.

 Vytvoř nový`Document` objekt a a`DocumentBuilder` k vytvoření dokumentu.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení sloupcového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme pět položek s jejich odpovídajícími hodnotami.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Krok 4: Přizpůsobte popisky os

 Chcete-li nastavit jednotku intervalu mezi štítky na ose X, přejděte na`AxisX` vlastnost grafu a nastavte`TickLabelSpacing` vlastnost na požadovanou hodnotu. V tomto příkladu nastavíme rozestup na 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Krok 5: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Tím je implementace nastavení jednotky intervalu mezi štítky na ose dokončena pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Interval Unit Between Labels On Axis pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Závěr

tomto tutoriálu jste se naučili, jak nastavit jednotku intervalu mezi štítky na ose grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit sloupcový graf, přidat data sérií a upravit popisky os tak, abyste řídili rozestupy mezi popisky.

Aspose.Words for .NET poskytuje výkonné funkce pro manipulaci s grafy v dokumentech aplikace Word. Nastavením jednotky intervalu mezi štítky na ose můžete ovládat hustotu zobrazení štítků a zlepšit čitelnost vašich grafů. To vám umožní optimalizovat prezentaci dat a zlepšit celkovou uživatelskou zkušenost.

S Aspose.Words for .NET máte možnost přizpůsobit různé aspekty grafu, včetně označení os. Můžete nastavit požadovanou jednotku intervalu, abyste zajistili, že jsou štítky vhodně rozmístěny a poskytují jasnou reprezentaci datových bodů.

### Nejčastější dotazy

#### Q1. Co jsou popisky os v grafu?
Popisky os v grafu odkazují na textovou reprezentaci hodnot podél vodorovné (osa X) nebo svislé (osa Y) grafu. Tyto popisky pomáhají identifikovat a interpretovat datové body vykreslené v grafu. Popisky os poskytují kontext a umožňují uživatelům porozumět měřítku a rozsahu hodnot v grafu.

#### Q2. Jak mohu přizpůsobit rozestupy mezi štítky os?
 Chcete-li upravit mezery mezi popisky os v grafu pomocí Aspose.Words for .NET, můžete přistupovat k`AxisX` nebo`AxisY` vlastnost grafu a upravit`TickLabelSpacing` vlastnictví. Nastavením`TickLabelSpacing` na konkrétní hodnotu, můžete řídit jednotku intervalu mezi štítky na příslušné ose a upravovat rozestupy podle vašich požadavků.

#### Q3. Mohu nastavit různé rozestupy pro popisky osy X a Y?
Ano, pomocí Aspose.Words for .NET můžete nastavit různé rozestupy pro popisky osy X a Y. Přístup k příslušné ose (`AxisX` pro osu X popř`AxisY` pro osu Y) grafu a upravte`TickLabelSpacing`vlastnost jednotlivě pro každou osu. To vám umožní mít různé intervalové jednotky a rozestupy pro popisky na ose X a Y, což poskytuje jemnou kontrolu nad vzhledem grafu.

#### Q4. Jaký význam má intervalová jednotka mezi popisky na ose?
Jednotka intervalu mezi štítky na ose určuje rozestupy mezi po sobě jdoucími štítky zobrazenými v grafu. Nastavením jednotky intervalu můžete řídit hustotu štítků a zajistit, aby byly vhodně rozmístěny, aby nedocházelo k přeplňování a překrývání. Úprava jednotky intervalu vám umožní prezentovat data čitelnějším a vizuálně přitažlivějším způsobem.

#### Q5. Mohu upravit další vlastnosti popisků os?
Ano, Aspose.Words for .NET poskytuje širokou škálu vlastností pro přizpůsobení vzhledu a chování popisků os. Můžete upravit vlastnosti, jako je písmo, velikost, barva, orientace, zarovnání a další, abyste dosáhli požadovaného formátování a stylu pro popisky os. Knihovna nabízí rozsáhlou kontrolu nad prvky grafu, což vám umožňuje vytvářet profesionálně vypadající grafy přizpůsobené vašim konkrétním požadavkům.