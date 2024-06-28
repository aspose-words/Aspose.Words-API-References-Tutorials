---
title: Přidejte hodnoty data a času na osu grafu
linktitle: Přidejte hodnoty data a času na osu grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se přidávat hodnoty data a času na osu grafu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/date-time-values-to-axis/
---

Tento tutoriál vysvětluje, jak přidat hodnoty data a času na osu grafu pomocí Aspose.Words for .NET.

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

## Krok 3: Vložení a konfigurace tvaru grafu
 Vložte tvar grafu do dokumentu pomocí`InsertChart` metoda`DocumentBuilder` objekt. Nastavte požadovaný typ a rozměry grafu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Krok 4: Přidejte data do grafu
Přidejte data do řady grafů, včetně hodnot data a času.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Krok 5: Nakonfigurujte osu
Nakonfigurujte osu X grafu pro zobrazení hodnot data a času.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Krok 6: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithCharts.DateTimeValuesToAxis.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Příklad zdrojového kódu pro Date Time Values To Axis pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Nastavte hlavní jednotky na týden a vedlejší jednotky na den.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Tento příklad kódu vytvoří nový dokument aplikace Word, vloží sloupcový graf s hodnotami data a času na ose X a uloží dokument do určeného adresáře.

## Závěr
tomto tutoriálu jste se naučili, jak přidat hodnoty data a času na osu grafu pomocí Aspose.Words for .NET. Podle podrobného průvodce můžete vytvořit graf, přidat hodnoty data a času do série a nakonfigurovat osu tak, aby zobrazovala hodnoty data a času přesně. Aspose.Words for .NET poskytuje výkonnou sadu funkcí pro textové zpracování s grafy v dokumentech aplikace Word, což vám umožňuje efektivně reprezentovat a vizualizovat data s hodnotami data a času.

### Nejčastější dotazy

#### Q1. Mohu přidat hodnoty data a času na osu grafu pomocí Aspose.Words for .NET?
Ano, pomocí Aspose.Words for .NET můžete přidávat a zobrazovat hodnoty data a času na ose grafu v dokumentu aplikace Word. Aspose.Words poskytuje rozhraní API a funkce pro práci s různými typy grafů a přizpůsobení jejich vzhledu, včetně zpracování hodnot data a času na ose.

#### Q2. Jak přidám hodnoty data a času do série grafu?
 Chcete-li přidat hodnoty data a času do řady grafů, můžete použít`Add`metoda řady grafu. Poskytněte pole hodnot data a času jako data kategorie (osa X) spolu s odpovídajícími hodnotami řady. To vám umožní vykreslit datové body s hodnotami data a času do grafu.

#### Q3. Jak mohu nakonfigurovat osu tak, aby zobrazovala hodnoty data a času?
 Nastavením příslušných vlastností můžete nakonfigurovat osu grafu tak, aby zobrazovala hodnoty data a času. Můžete například zadat minimální a maximální hodnoty pro osu pomocí`Scaling.Minimum` a`Scaling.Maximum` vlastnosti, resp. Kromě toho můžete nastavit hlavní a vedlejší jednotky pro definování intervalu a značek pro osu.
