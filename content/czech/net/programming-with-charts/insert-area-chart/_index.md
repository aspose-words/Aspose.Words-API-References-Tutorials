---
title: Vložit plošný graf do dokumentu aplikace Word
linktitle: Vložit plošný graf do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit plošný graf do dokumentu pomocí Aspose.Words for .NET. Přidejte data série a uložte dokument s grafem.
type: docs
weight: 10
url: /cs/net/programming-with-charts/insert-area-chart/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k vložení plošného grafu do dokumentu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a uložit dokument.

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

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení plošného grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme pět datových bodů s odpovídajícími daty a hodnotami.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Tím je implementace vkládání plošného grafu pomocí Aspose.Words pro .NET dokončena.

### Příklad zdrojového kódu pro vložení plošného grafu pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Závěr

V tomto tutoriálu jste se naučili, jak vložit plošný graf do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit plošný graf, přidat data sérií a uložit dokument s grafem.

Aspose.Words for .NET poskytuje výkonné rozhraní API pro textové zpracování s grafy v dokumentech aplikace Word. Pomocí několika řádků kódu můžete vytvořit profesionálně vypadající plošné grafy a upravit je podle svých požadavků. Plošné grafy se běžně používají k zobrazení velikosti a trendů dat v průběhu času nebo kategorií.

Pomocí Aspose.Words for .NET můžete automatizovat proces generování dokumentů s plošnými grafy, což ušetří čas a námahu při ručním vytváření dokumentů. Knihovna nabízí širokou škálu typů grafů a možností přizpůsobení, což vám umožní vytvářet vizuálně přitažlivé a informativní grafy v dokumentech aplikace Word.

### Nejčastější dotazy

#### Q1. Co je Aspose.Words for .NET?
Aspose.Words for .NET je výkonná knihovna pro zpracování dokumentů, která umožňuje vývojářům vytvářet, upravovat a převádět dokumenty aplikace Word programově v aplikacích .NET. Poskytuje komplexní sadu rozhraní API pro zpracování textu s prvky dokumentu, včetně grafů, odstavců, tabulek a dalších.

#### Q2. Jak nainstaluji Aspose.Words for .NET?
Chcete-li nainstalovat Aspose.Words for .NET, můžete použít správce balíčků NuGet v sadě Visual Studio k instalaci knihovny přímo do vašeho projektu. Jednoduše vyhledejte „Aspose.Words“ ve správci balíčků NuGet a nainstalujte balíček.

#### Q3. Mohu přizpůsobit vzhled plošného grafu?
Ano, pomocí Aspose.Words for .NET můžete přizpůsobit různé aspekty vzhledu plošného grafu. Můžete upravit vlastnosti, jako je název grafu, barva řady, popisky os a formátování oblasti grafu. Knihovna poskytuje bohatou sadu rozhraní API pro ovládání vizuálních prvků grafu a vytvoření přizpůsobeného vzhledu, který vyhovuje vašim potřebám.

#### Q4. Mohu do plošného grafu přidat více řad?
Ano, pomocí Aspose.Words for .NET můžete do plošného grafu přidat více řad. Každá řada představuje sadu datových bodů, které jsou vyneseny do grafu. Můžete přidat řady s různými sadami dat a přizpůsobit každou řadu jednotlivě, včetně jejího názvu, datových bodů a vzhledu.

#### Q5. Mohu uložit dokument s vloženým plošným grafem v různých formátech?
 Ano, Aspose.Words for .NET umožňuje uložit dokument s vloženým plošným grafem v různých formátech, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat požadovaný výstupní formát na základě vašich požadavků a použít`Save` metoda`Document` objekt pro uložení dokumentu. Vložený plošný graf zůstane v uloženém dokumentu zachován.

#### Q6. Mohu upravit data a vzhled plošného grafu po jeho vložení?
Ano, po vložení plošného grafu do dokumentu můžete upravit jeho data a vzhled pomocí API poskytovaných Aspose.Words pro .NET. Můžete aktualizovat data řady, změnit typ grafu, přizpůsobit vlastnosti osy a použít možnosti formátování k vytvoření dynamických a interaktivních grafů v dokumentech aplikace Word.