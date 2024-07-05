---
title: Definujte vlastnosti osy XY v grafu
linktitle: Definujte vlastnosti osy XY v grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se definovat vlastnosti osy XY v grafu pomocí Aspose.Words for .NET. Jsou ukázány možnosti přizpůsobení pro osy X a Y.
type: docs
weight: 10
url: /cs/net/programming-with-charts/define-xyaxis-properties/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k definování vlastností pro osy X a Y v grafu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a přizpůsobit vlastnosti osy.

## Krok 1: Nastavte projekt

Ujistěte se, že máte následující předpoklady:

- Nainstalovaná knihovna Aspose.Words for .NET. Můžete si jej stáhnout pomocí správce balíčků NuGet k instalaci.
- Cesta k adresáři dokumentu, kam bude výstupní dokument uložen.

## Krok 2: Vytvořte nový dokument a vložte graf

 Vytvoř nový`Document` objekt a a`DocumentBuilder` k vytvoření dokumentu.

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dále vložte graf do dokumentu pomocí`InsertChart` metoda`DocumentBuilder`. V tomto příkladu vložíme plošný graf.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme pět datových bodů s odpovídajícími daty a hodnotami.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Krok 4: Přizpůsobte vlastnosti os X a Y

 Chcete-li přizpůsobit vlastnosti os X a Y, přejděte na`ChartAxis` objekty spojené s grafem.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Upravte vlastnosti`xAxis` a`yAxis`objektů a nastavte požadované možnosti pro osy X a Y. V tomto příkladu si ukážeme některé běžné vlastnosti, které lze přizpůsobit.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Krok 5: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Tím je dokončena implementace definování vlastností osy XY v grafu pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Define XYAxis Properties pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Vložit graf
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Změňte osu X na kategorii namísto data, takže všechny body budou umístěny se stejným intervalem na ose X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Měřeno v zobrazovacích jednotkách osy Y (stovky).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak definovat vlastnosti pro osy X a Y v grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce můžete vytvořit graf, přidat data řady a přizpůsobit vlastnosti osy tak, aby vyhovovaly vašim konkrétním požadavkům. Aspose.Words for .NET poskytuje komplexní rozhraní API pro textové zpracování s grafy v dokumentech aplikace Word, které vám umožňuje manipulovat s různými aspekty grafu, včetně os.

Přístupem k`ChartAxis` objektů spojených s grafem, můžete upravit vlastnosti, jako je typ kategorie, křížení os, značky zatržení, pozice štítků, měřítko a další. Tato flexibilita vám umožňuje přizpůsobit vzhled a chování os grafu tak, abyste efektivně prezentovali svá data.

Pomocí Aspose.Words for .NET můžete bezproblémově integrovat možnosti tvorby grafů a přizpůsobení do aplikací .NET a automatizovat generování profesionálně vypadajících dokumentů s bohatými vizualizacemi.

### Nejčastější dotazy

#### Q1. Co je Aspose.Words for .NET?
Aspose.Words for .NET je výkonná knihovna pro zpracování dokumentů, která umožňuje vývojářům vytvářet, manipulovat a ukládat dokumenty Word programově v aplikacích .NET. Poskytuje širokou škálu funkcí pro textové zpracování s prvky dokumentu, včetně grafů.

#### Q2. Jak mohu nainstalovat Aspose.Words pro .NET?
Aspose.Words for .NET můžete nainstalovat stažením pomocí správce balíčků NuGet v sadě Visual Studio. Jednoduše vyhledejte „Aspose.Words“ ve správci balíčků NuGet a nainstalujte jej do svého projektu.

#### Q3. Mohu upravit další aspekty grafu pomocí Aspose.Words pro .NET?
Ano, Aspose.Words for .NET poskytuje rozsáhlé možnosti pro přizpůsobení různých aspektů grafu. Kromě definování vlastností os můžete upravit typ grafu, datovou řadu, legendu, nadpis, oblast vykreslení, popisky dat a mnoho dalších prvků grafu. Rozhraní API nabízí jemnou kontrolu nad vzhledem a chováním grafu.

#### Q4. Mohu pomocí Aspose.Words for .NET vytvářet různé typy grafů?
 Ano, Aspose.Words for .NET podporuje širokou škálu typů grafů, včetně plošných, pruhových, čárových, koláčových, bodových a dalších. Můžete použít`ChartType` výčtu k určení požadovaného typu grafu při vkládání tvaru grafu do dokumentu aplikace Word.

#### Q5. Mohu uložit graf v různých formátech?
Ano, Aspose.Words for .NET umožňuje uložit dokument obsahující graf v různých formátech, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat vhodný formát na základě vašich požadavků a použít jej`Save` metoda`Document` objekt pro uložení dokumentu.

#### Q6. Mohu tyto techniky použít na více grafů v dokumentu?
 Ano, tyto techniky můžete použít na více grafů v dokumentu opakováním nezbytných kroků pro každý graf. Můžete vytvořit oddělené`Chart` a`ChartAxis` objektů pro každý graf a podle toho přizpůsobte jejich vlastnosti. Aspose.Words for .NET poskytuje plnou podporu pro textové zpracování s více grafy v jednom dokumentu.