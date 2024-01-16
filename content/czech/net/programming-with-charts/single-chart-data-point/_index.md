---
title: Přizpůsobte jeden datový bod grafu v grafu
linktitle: Přizpůsobte jeden datový bod grafu v grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak upravit jeden datový bod v grafu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/single-chart-data-point/
---

Tento kurz vysvětluje, jak používat Aspose.Words pro .NET k přizpůsobení jednoho datového bodu v grafu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, získat přístup ke konkrétním datovým bodům a upravit jejich vlastnosti.

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

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení spojnicového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přístup k datovým bodům a jejich přizpůsobení

 Chcete-li upravit jednotlivé datové body, musíte mít přístup k`ChartDataPointCollection` řady a pomocí indexu vyberte požadovaný datový bod.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Tím je dokončena implementace přizpůsobení jednoho datového bodu v grafu pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro Single Chart Data Point pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak upravit jeden datový bod v grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit spojnicový graf, získat přístup ke konkrétním datovým bodům v řadě grafů a upravit jejich vlastnosti, abyste dosáhli požadovaného přizpůsobení.

Aspose.Words for .NET poskytuje výkonné funkce pro manipulaci s grafy v dokumentech aplikace Word. Přístupem k jednotlivým datovým bodům v rámci řady grafů můžete použít specifické úpravy k přizpůsobení jejich vzhledu a chování. To vám umožní zvýraznit konkrétní datové body, změnit symboly značek, upravit velikosti značek a další, abyste zlepšili vizuální reprezentaci grafu.

Přizpůsobení jednotlivých datových bodů vám dává flexibilitu zdůraznit důležitá data nebo zvýraznit konkrétní trendy v grafu. S Aspose.Words for .NET můžete snadno přistupovat a upravovat datové body v různých typech grafů, což vám umožňuje vytvářet vizuálně přitažlivé a informativní grafy v dokumentech aplikace Word.

### Nejčastější dotazy

#### Q1. Mohu přizpůsobit více datových bodů v grafu?
 Ano, pomocí Aspose.Words for .NET můžete upravit více datových bodů v grafu. Přístupem k`ChartDataPointCollection`série, můžete vybrat a upravit více datových bodů na základě jejich indexů. Pomocí smyčky nebo jednotlivých přiřazení upravte požadované vlastnosti pro každý datový bod. Tímto způsobem můžete použít různá přizpůsobení na více datových bodů ve stejném grafu.

#### Q2. Jak mohu změnit symbol značky pro datový bod?
 Chcete-li změnit symbol značky pro datový bod v grafu pomocí Aspose.Words for .NET, musíte`Marker` vlastnictvím`ChartDataPoint` objekt a nastavte`Symbol` vlastnost na požadovaný symbol značky. Symboly značek představují tvar nebo ikonu použité k reprezentaci každého datového bodu v grafu. Můžete si vybrat z různých vestavěných symbolů značek, jako je kruh, čtverec, kosočtverec, trojúhelník, hvězda a další.

#### Q3. Mohu upravit velikost značky datového bodu?
 Ano, velikost značky datového bodu v grafu můžete upravit pomocí Aspose.Words for .NET. Přístup k`Marker` vlastnictvím`ChartDataPoint` objekt a nastavte`Size`vlastnost na požadovanou velikost značky. Velikost značky je obvykle specifikována v bodech, kde větší hodnota představuje větší velikost značky. Úprava velikosti značky vám umožní zdůraznit konkrétní datové body nebo je odlišit na základě jejich významnosti.

#### Q4. Jaké další vlastnosti mohu upravit pro datový bod?
Aspose.Words for .NET poskytuje řadu vlastností, které můžete upravit pro datový bod v grafu. Některé z běžně upravovaných vlastností zahrnují symbol značky, velikost značky, barvu značky, viditelnost datového štítku, výbuch, převrácení, pokud je negativní a další. Tyto vlastnosti vám umožňují přizpůsobit vzhled, chování a interaktivitu jednotlivých datových bodů, což vám umožní vytvářet grafy přizpůsobené vašim konkrétním požadavkům.

#### Q5. Mohu přizpůsobit datové body v jiných typech grafů?
Ano, pomocí Aspose.Words for .NET můžete upravit datové body v různých typech grafů. I když tento kurz demonstruje přizpůsobení datových bodů ve spojnicovém grafu, podobné techniky můžete použít i na jiné typy grafů, jako jsou sloupcové grafy, sloupcové grafy, výsečové grafy a další. Proces zahrnuje přístup k řadám a datovým bodům v grafu a odpovídajícím způsobem upravit jejich vlastnosti.