---
title: Skrýt osu grafu v dokumentu aplikace Word
linktitle: Skrýt osu grafu v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se skrýt osu grafu v dokumentu pomocí Aspose.Words for .NET. Skrytím osy získáte čistší a cílenější zobrazení grafu.
type: docs
weight: 10
url: /cs/net/programming-with-charts/hide-chart-axis/
---

Tento tutoriál vysvětluje, jak pomocí Aspose.Words for .NET skrýt osu grafu v dokumentu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a skrýt osu grafu.

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

 Dále vložte graf do dokumentu pomocí`InsertChart` metoda`DocumentBuilder`. V tomto příkladu vložíme sloupcový graf.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme pět položek a jejich odpovídající hodnoty.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Krok 4: Skryjte osu grafu

 Chcete-li skrýt osu grafu, otevřete`AxisY` vlastnost grafu a nastavte`Hidden`majetek do`true`.

```csharp
chart.AxisY.Hidden = true;
```

tomto příkladu skryjeme osu Y grafu.

## Krok 5: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Tím je implementace skrytí osy grafu pomocí Aspose.Words pro .NET dokončena.

### Příklad zdrojového kódu pro Hide Chart Axis pomocí Aspose.Words pro .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak skrýt osu grafu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit graf, přidat data sérií a skrýt osu grafu, abyste dosáhli požadovaného vizuálního efektu.

 Aspose.Words for .NET poskytuje komplexní rozhraní API pro textové zpracování s grafy v dokumentech aplikace Word, které vám umožňuje manipulovat s různými aspekty grafu, včetně vlastností os. Přístupem k`AxisY` vlastnost grafu, můžete skrýt osu Y a odstranit ji z vizualizace grafu.

Skrytí osy grafu může být užitečné, když se chcete zaměřit na data grafu bez rozptylování čar a popisků os. Poskytuje čistší a minimalistický vzhled grafu.

Pomocí Aspose.Words for .NET můžete snadno začlenit možnosti vytváření grafů do svých aplikací .NET a vytvářet profesionálně vypadající dokumenty s přizpůsobenými grafy a skrytými osami grafů.

### Nejčastější dotazy

#### Q1. Co je Aspose.Words for .NET?
Aspose.Words for .NET je výkonná knihovna pro zpracování dokumentů, která umožňuje vývojářům vytvářet, manipulovat a ukládat dokumenty Word programově v aplikacích .NET. Poskytuje širokou škálu funkcí pro textové zpracování s prvky dokumentu, včetně grafů a os grafů.

#### Q2. Jak mohu nainstalovat Aspose.Words pro .NET?
Aspose.Words for .NET můžete nainstalovat stažením pomocí správce balíčků NuGet v sadě Visual Studio. Jednoduše vyhledejte „Aspose.Words“ ve správci balíčků NuGet a nainstalujte jej do svého projektu.

#### Q3. Mohu skrýt jak osu X, tak osu Y grafu?
 Ano, pomocí Aspose.Words for .NET můžete skrýt jak osu X, tak osu Y grafu. Chcete-li skrýt osu X, můžete získat přístup k`AxisX` vlastnost grafu a nastavte`Hidden`majetek do`true` . Podobně, chcete-li skrýt osu Y, můžete získat přístup k`AxisY` vlastnost a nastavte`Hidden`majetek do`true`. To vám umožní odstranit obě osy z vizualizace grafu.

#### Q4. Mohu po skrytí osu znovu zobrazit?
Ano, po skrytí můžete osu grafu znovu zobrazit pomocí Aspose.Words for .NET. Chcete-li zobrazit skrytou osu, jednoduše nastavte`Hidden` vlastnost odpovídající`AxisX` nebo`AxisY` namítat proti`false`. Tím se osa v grafu opět zviditelní.

#### Q5. Mohu přizpůsobit další vlastnosti osy grafu?
 Ano, Aspose.Words for .NET umožňuje přizpůsobit různé vlastnosti osy grafu, jako je název osy, popisky, barva čáry a další. Přístupem k`AxisX` a`AxisY` vlastnosti grafu, můžete upravit vlastnosti jako`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, a mnoho dalších. To vám dává jemnou kontrolu nad vzhledem a chováním osy grafu.

#### Q6. Mohu uložit graf se skrytou osou v různých formátech souborů?
 Ano, Aspose.Words for .NET umožňuje uložit dokument obsahující graf se skrytou osou v různých formátech souborů, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat požadovaný výstupní formát na základě vašich požadavků a použít`Save` metoda`Document` objekt pro uložení dokumentu. Skrytá osa zůstane v uloženém dokumentu zachována.