---
title: Přizpůsobit štítek dat grafu
linktitle: Přizpůsobit štítek dat grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se přidávat a přizpůsobovat štítky dat v grafu pomocí Aspose.Words for .NET, abyste poskytli další informace o datových bodech.
type: docs
weight: 10
url: /cs/net/programming-with-charts/chart-data-label/
---

Tento výukový program vysvětluje, jak přidat a upravit štítky dat v grafu pomocí Aspose.Words for .NET. Datové štítky poskytují další informace o datových bodech v grafu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte nový dokument a DocumentBuilder
 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder` objekt pracovat s dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložte a nakonfigurujte graf
 Vložte graf do dokumentu pomocí`InsertChart` metoda`DocumentBuilder` objekt. Nastavte požadovaný typ a rozměry grafu.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Krok 4: Přizpůsobte štítky dat
Získejte přístup ke sbírce štítků dat řady grafů a upravte různé vlastnosti, abyste přizpůsobili vzhled štítků dat.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Krok 5: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu uložíme dokument jako "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Příklad zdrojového kódu pro Chart Data Label pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Ve výchozím nastavení, když k datovým bodům ve výsečovém grafu přidáte popisky dat, zobrazí se odkazové čáry pro popisky dat, které jsou
	// umístěn daleko mimo konec datových bodů. Odkazové čáry vytvářejí vizuální spojení mezi datovým štítkem a jeho
	// odpovídající datový bod.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

A je to! Úspěšně jste přidali a přizpůsobili štítky dat v grafu pomocí Aspose.Words pro .NET.

## Závěr
tomto tutoriálu jste se naučili přidávat a přizpůsobovat štítky dat v grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce můžete vložit graf, získat přístup ke kolekci štítků dat a upravit vlastnosti, abyste přizpůsobili vzhled štítků dat. Aspose.Words for .NET poskytuje výkonné rozhraní API pro zpracování textu s dokumenty a grafy aplikace Word, které vám umožňuje vytvářet vizuálně přitažlivé a informativní grafy s přizpůsobenými štítky dat.

### Nejčastější dotazy

#### Q1. Co jsou štítky dat v grafu?
Popisky dat v grafu poskytují další informace o datových bodech znázorněných v grafu. Mohou zobrazovat hodnoty, kategorie, názvy řad, procenta nebo jiné relevantní podrobnosti v závislosti na typu a konfiguraci grafu.

#### Q2. Mohu přizpůsobit vzhled štítků s údaji?
Ano, vzhled štítků dat v grafu můžete přizpůsobit. Aspose.Words for .NET poskytuje možnosti úpravy různých vlastností datových štítků, jako je zobrazení klíčů legend, odkazových čar, názvů kategorií, názvů řad, hodnot a dalších. Můžete také nastavit oddělovače a formátovat štítky tak, aby vyhovovaly vašim specifickým požadavkům.

#### Q3. Mohu přidat štítky dat k libovolnému typu grafu?
Ano, štítky dat můžete přidávat do různých typů grafů, včetně sloupcových grafů, koláčových grafů, spojnicových grafů a dalších. Proces přidávání a přizpůsobení štítků dat se může mírně lišit v závislosti na typu grafu a knihovně nebo nástroji, který používáte.
