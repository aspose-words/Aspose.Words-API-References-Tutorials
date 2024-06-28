---
title: Nastavit výchozí možnosti pro štítky dat v grafu
linktitle: Nastavit výchozí možnosti pro štítky dat v grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak nastavit výchozí možnosti pro popisky dat v grafu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/default-options-for-data-labels/
---

Tento kurz vysvětluje, jak používat Aspose.Words pro .NET k nastavení výchozích možností pro popisky dat v grafu. Poskytnutý kód ukazuje, jak vytvořit graf, přidat datové řady a přizpůsobit štítky dat pomocí Aspose.Words.

## Krok 1: Nastavte projekt

Než začneme, ujistěte se, že máte splněny následující požadavky:

- Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout pomocí správce balíčků NuGet a nainstalovat jej.
- Cesta k adresáři dokumentu, kam bude výstupní dokument uložen.

## Krok 2: Vytvořte nový dokument a vložte graf.

 Nejprve vytvoříme nový`Document` objekt a a`DocumentBuilder` k vytvoření dokumentu.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dále vložíme graf do dokumentu pomocí`InsertChart` metoda`DocumentBuilder`. V tomto příkladu vložíme výsečový graf.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte datové řady do grafu

Nyní do grafu přidáme datovou řadu. V tomto příkladu přidáme tři kategorie a jejich odpovídající hodnoty.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Krok 4: Přizpůsobte štítky dat

 Abychom mohli upravit štítky dat v grafu, potřebujeme přístup k`ChartDataLabelCollection` objekt spojený se sérií.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Poté můžeme modifikovat různé vlastnosti`labels`objekt pro nastavení požadovaných možností pro popisky dat. V tomto příkladu povolíme zobrazení procenta a hodnoty, zakážeme odkazové čáry a nastavíme vlastní oddělovač.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Krok 5: Uložte dokument

 Nakonec dokument uložíme do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Tím je implementace nastavení výchozích možností pro popisky dat v grafu dokončena pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro výchozí možnosti pro datové štítky pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak nastavit výchozí možnosti pro popisky dat v grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce můžete vytvořit graf, přidat datové řady a přizpůsobit štítky dat tak, aby vyhovovaly vašim konkrétním požadavkům. Aspose.Words for .NET poskytuje výkonné rozhraní API pro textové zpracování s grafy v dokumentech aplikace Word, které vám umožňuje manipulovat s různými prvky grafu a dosáhnout požadovaného vzhledu a funkčnosti.

 Nastavením vlastností`ChartDataLabelCollection`objekt spojený s řadou grafů, můžete ovládat zobrazení popisků dat, včetně možností, jako je zobrazení procent, hodnot, odkazových čar a vlastních oddělovačů. Tato flexibilita vám umožňuje efektivně prezentovat data a zlepšit vizuální reprezentaci vašich grafů.

### Nejčastější dotazy

#### Q1. Co je Aspose.Words for .NET?
Aspose.Words for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a ukládat dokumenty Wordu programově pomocí aplikací .NET. Poskytuje širokou škálu funkcí pro textové zpracování s prvky dokumentu, včetně grafů.

#### Q2. Jak mohu nainstalovat Aspose.Words pro .NET?
Aspose.Words for .NET můžete nainstalovat stažením pomocí správce balíčků NuGet v sadě Visual Studio. Jednoduše vyhledejte „Apose.Words“ ve správci balíčků NuGet a nainstalujte jej do svého projektu.

#### Q3. Mohu upravit další aspekty grafu pomocí Aspose.Words pro .NET?
Ano, Aspose.Words for .NET umožňuje přizpůsobit různé aspekty grafu, jako je typ grafu, popisky os, legenda, plocha grafu a další. Můžete přistupovat k různým vlastnostem objektu grafu a upravovat je, abyste dosáhli požadovaného vzhledu a chování.

#### Q4. Mohu uložit graf v různých formátech?
 Ano, Aspose.Words for .NET podporuje ukládání dokumentu obsahujícího graf v různých formátech, včetně DOCX, PDF, HTML a dalších. Můžete si vybrat vhodný formát na základě vašich požadavků a použít jej`Save` metoda`Document` objekt pro uložení dokumentu.

#### Q5. Mohu tyto techniky použít na jiné typy grafů?
Ano, techniky popsané v tomto tutoriálu lze aplikovat na jiné typy grafů podporované Aspose.Words for .NET. Klíčem je přístup k relevantním objektům a vlastnostem specifickým pro typ grafu, se kterým zpracováváte text.