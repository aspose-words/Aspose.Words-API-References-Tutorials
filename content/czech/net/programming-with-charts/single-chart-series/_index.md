---
title: Přizpůsobte jednu řadu grafů v grafu
linktitle: Přizpůsobte jednu řadu grafů v grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak přizpůsobit jednotlivé řady grafů v grafu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/single-chart-series/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k přizpůsobení jednotlivých řad grafů v grafu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, získat přístup ke konkrétním řadám a upravit jejich vlastnosti.

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

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení spojnicového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přístup k řadě grafů a jejich přizpůsobení

 Chcete-li upravit jednu řadu grafů, musíte mít přístup k`ChartSeries` objekty grafu.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Tím je dokončena implementace přizpůsobení jedné řady grafů pomocí Aspose.Words pro .NET.

### Příklad zdrojového kódu pro Single Chart Series pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Můžete také určit, zda má být čára spojující body v grafu vyhlazena pomocí Catmull-Rom splajnů.
	series0.Smooth = true;
	series1.Smooth = true;
	// Určuje, zda má nadřazený prvek ve výchozím nastavení invertovat své barvy, pokud je hodnota záporná.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak upravit jednu řadu grafu v grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit spojnicový graf, získat přístup ke konkrétním sériím grafů a upravit jejich vlastnosti, abyste dosáhli požadovaného přizpůsobení.

Aspose.Words for .NET poskytuje výkonné funkce pro manipulaci s grafy v dokumentech aplikace Word. Přístupem k jednotlivým řadám grafů můžete použít konkrétní úpravy a přizpůsobit jejich vzhled a chování. To vám umožní změnit název řady, povolit vyhlazení čáry grafu, přizpůsobit značky pro datové body, invertovat barvy pro záporné hodnoty a další pro vylepšení vizuální reprezentace vašeho grafu.

Přizpůsobení jedné řady grafů vám poskytuje flexibilitu pro zvýraznění konkrétních dat nebo zdůraznění konkrétních trendů v grafu. S Aspose.Words for .NET můžete snadno přistupovat a upravovat vlastnosti řad grafů, což vám umožňuje vytvářet vizuálně přitažlivé a informativní grafy ve vašich dokumentech aplikace Word.

### Nejčastější dotazy

#### Q1. Mohu přizpůsobit více řad grafů v grafu?
 Ano, pomocí Aspose.Words for .NET můžete upravit více řad grafů v grafu. Přístupem k`ChartSeries`objektů v grafu, můžete vybrat a upravit více řad na základě jejich indexů nebo specifických kritérií. Pomocí smyčky nebo jednotlivých přiřazení upravte požadované vlastnosti pro každou řadu grafů. Tímto způsobem můžete použít různá přizpůsobení na více řad ve stejném grafu.

#### Q2. Jak mohu změnit název řady grafů?
 Chcete-li změnit název řady grafu v grafu pomocí Aspose.Words for .NET, musíte mít přístup k`Name` vlastnictvím`ChartSeries` objekt a nastavte jej na požadovaný název. Název série se obvykle zobrazuje v legendě grafu nebo v popiscích dat a poskytuje popisný štítek pro sérii. Úpravou názvu řady můžete poskytnout smysluplné názvy, které odrážejí data reprezentovaná každou řadou.

#### Q3. Co je vyhlazování řad grafů?
Vyhlazení řad grafů je technika vizuálního vylepšení, která umožňuje vytvořit hladkou čáru spojující body v grafu. Aplikuje vyhlazovací algoritmus, jako jsou Catmull-Rom splajny, k interpolaci mezi datovými body a vytvoření vizuálně příjemné křivky. Chcete-li povolit vyhlazování řad v grafu pomocí Aspose.Words pro .NET, přejděte na`Smooth` vlastnictvím`ChartSeries` objekt a nastavte jej na`true`. Vyhlazování může být užitečné pro zobrazení trendů nebo vzorů v datech s nepravidelnými výkyvy.

#### Q4. Jak mohu přizpůsobit značky pro datové body v řadě grafů?
 Chcete-li upravit značky pro datové body v řadě grafů pomocí Aspose.Words for .NET, musíte mít přístup k`Marker` vlastnictvím`ChartSeries` objektu a upravovat jeho vlastnosti jako např`Symbol` a`Size`. Značky jsou vizuální indikátory umístěné na grafu, které představují jednotlivé datové body. Můžete si vybrat z různých vestavěných symbolů značek a upravit jejich velikost, abyste zvýraznili nebo odlišili konkrétní datové body v rámci série.

#### Q5. Mohu invertovat barvy pro záporné hodnoty v řadě grafů?
 Ano, můžete invertovat barvy pro záporné hodnoty v řadě grafů pomocí Aspose.Words for .NET. Nastavením`InvertIfNegative` vlastnictvím`ChartSeries` namítat proti`true`, budou barvy datových bodů se zápornými hodnotami invertovány, takže budou vizuálně odlišné od kladných hodnot. Tato funkce může být užitečná při porovnávání kladných a záporných hodnot v řadě grafů a poskytuje jasné rozlišení mezi těmito dvěma.