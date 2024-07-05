---
title: Formát Počet Datových štítků V Grafu
linktitle: Formát Počet Datových štítků V Grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se formátovat počet štítků dat v grafu pomocí Aspose.Words for .NET. Snadno přizpůsobte formáty čísel pro datové štítky.
type: docs
weight: 10
url: /cs/net/programming-with-charts/format-number-of-data-label/
---

Tento kurz vysvětluje, jak používat Aspose.Words pro .NET k formátování počtu štítků dat v grafu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a přizpůsobit formát čísel štítků dat.

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

 Dále vložte graf do dokumentu pomocí`InsertChart` metoda`DocumentBuilder`. V tomto příkladu vložíme spojnicový graf.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme tři kategorie a jejich odpovídající hodnoty.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Krok 4: Přizpůsobte formát čísel štítků dat

 Chcete-li formátovat počet datových štítků, přejděte na`DataLabels` kolekce spojená se seriálem.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

V tomto příkladu jsme pro každý datový štítek nastavili různé formáty čísel. První datový štítek je formátován jako měna, druhý jako datum a třetí jako procento.

## Krok 5: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Tím je dokončena implementace formátování počtu štítků dat v grafu pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro štítek Format Number Of Data pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Smazat výchozí vygenerované série.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Nebo můžete nastavit kód formátu tak, aby byl propojen se zdrojovou buňkou,
	// tomto případě bude NumberFormat resetován na obecný a zděděn ze zdrojové buňky.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak formátovat počet datových štítků v grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit graf, přidat data sérií a upravit číselný formát štítků dat podle vašich požadavků.

 Aspose.Words for .NET poskytuje komplexní rozhraní API pro zpracování textu s grafy v dokumentech aplikace Word, což vám umožňuje manipulovat s různými aspekty grafu, včetně štítků dat. Přístupem k`DataLabels` kolekce spojené s řadou, můžete přizpůsobit formát čísel jednotlivých štítků dat.

Rozhraní API umožňuje ovládat zobrazení hodnot, nastavit různé formáty čísel pro každý štítek dat a propojit formát čísla se zdrojovou buňkou. Tato flexibilita vám umožňuje prezentovat číselná data v grafech s požadovaným formátováním, jako jsou symboly měn, formáty data a procentuální hodnoty.

Pomocí Aspose.Words for .NET můžete do svých aplikací .NET začlenit výkonné funkce pro vytváření grafů a vytvářet profesionálně vypadající dokumenty s plně formátovanými grafy a datovými štítky.

### Nejčastější dotazy

#### Q1. Co je Aspose.Words for .NET?
Aspose.Words for .NET je knihovna pro zpracování dokumentů s bohatými funkcemi, která umožňuje vývojářům vytvářet, manipulovat a ukládat dokumenty Word programově v aplikacích .NET. Poskytuje širokou škálu funkcí pro textové zpracování s prvky dokumentu, včetně grafů a datových štítků.

#### Q2. Jak mohu nainstalovat Aspose.Words pro .NET?
Aspose.Words for .NET můžete nainstalovat stažením pomocí správce balíčků NuGet v sadě Visual Studio. Jednoduše vyhledejte „Aspose.Words“ ve správci balíčků NuGet a nainstalujte jej do svého projektu.

#### Q3. Mohu formátovat další aspekty grafu pomocí Aspose.Words for .NET?
Ano, Aspose.Words for .NET poskytuje rozsáhlé možnosti pro formátování různých aspektů grafu. Kromě popisků dat můžete přizpůsobit typ grafu, data řady, vlastnosti os, legendu, nadpis, oblast vykreslování a mnoho dalších prvků grafu. Rozhraní API nabízí jemnou kontrolu nad vzhledem a formátováním grafu.

#### Q4. Mohu použít různé formáty čísel na různé štítky dat ve stejné řadě?
Ano, Aspose.Words for .NET umožňuje použít různé formáty čísel na jednotlivé štítky dat v rámci stejné řady. Přístupem k`DataLabels` kolekce přidružená k sérii, můžete nastavit`FormatCode` vlastnost každého datového štítku k určení požadovaného formátu čísla. To vám umožní prezentovat číselné hodnoty v různých formátech v rámci stejného grafu.

#### Q5. Mohu pro datové štítky použít vlastní číselné formáty?
 Ano, Aspose.Words for .NET podporuje vlastní číselné formáty pro štítky dat. Požadovaný formát čísla můžete určit nastavením`FormatCode` vlastnost datového štítku na kód vlastního formátu. To vám dává flexibilitu při použití široké škály formátů čísel, jako jsou symboly měn, formáty data, procentuální hodnoty a další.

#### Q6. Mohu uložit graf s formátovanými datovými štítky v různých formátech?
Ano, Aspose.Words for .NET umožňuje uložit dokument obsahující graf s formátovanými datovými štítky v různých formátech, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat vhodný formát na základě vašich požadavků a použít jej`Save` metoda`Document` objekt pro uložení dokumentu. Formátované datové štítky zůstanou v uloženém dokumentu zachovány.