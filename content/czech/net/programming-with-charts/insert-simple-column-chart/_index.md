---
title: Vložit jednoduchý sloupcový graf do dokumentu aplikace Word
linktitle: Vložit jednoduchý sloupcový graf do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit jednoduchý sloupcový graf do dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/insert-simple-column-chart/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k vložení jednoduchého sloupcového grafu do dokumentu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a uložit dokument.

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

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení sloupcového grafu do dokumentu. Můžete zadat různé typy a velikosti grafů podle vašich požadavků.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme několik sérií se dvěma kategoriemi.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Tím je implementace vkládání jednoduchého sloupcového grafu pomocí Aspose.Words pro .NET dokončena.

### Příklad zdrojového kódu pro Insert Simple Column Chart pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Můžete zadat různé typy a velikosti grafů.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Smazat výchozí vygenerované série.
	seriesColl.Clear();
	// Vytvořte pole názvů kategorií, v tomto tutoriálu máme dvě kategorie.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Upozorňujeme, že datová pole nesmí být prázdná a pole musí mít stejnou velikost.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Závěr

tomto tutoriálu jste se naučili, jak vložit jednoduchý sloupcový graf do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit sloupcový graf, přidat více řad s kategoriemi a odpovídajícími hodnotami a uložit dokument s grafem.

Aspose.Words for .NET poskytuje výkonné a flexibilní rozhraní API pro textové zpracování s grafy v dokumentech aplikace Word. Jednoduchý sloupcový graf je efektivní způsob, jak reprezentovat a porovnávat data v různých kategoriích. S Aspose.Words for .NET můžete snadno vytvářet sloupcové grafy s vlastními daty, přidávat více řad pro vizuální srovnání a upravovat vzhled grafu podle vašich požadavků.

Pomocí Aspose.Words for .NET můžete automatizovat proces generování dokumentů se sloupcovými grafy, což ušetří čas a námahu při ručním vytváření dokumentů. Knihovna nabízí širokou škálu typů grafů, včetně jednoduchých sloupcových grafů, a poskytuje různé možnosti přizpůsobení pro přizpůsobení vzhledu grafu vašim potřebám.

### Nejčastější dotazy

#### Q1. Co je sloupcový graf?
Sloupcový graf je typ grafu, který zobrazuje data pomocí svislých pruhů různé výšky. Každý sloupec představuje kategorii a výška sloupce odpovídá hodnotě této kategorie. Sloupcové grafy se běžně používají k porovnání dat v různých kategoriích nebo ke sledování změn v průběhu času.

#### Q2. Mohu do sloupcového grafu přidat více řad?
Ano, pomocí Aspose.Words for .NET můžete do sloupcového grafu přidat více řad. Každá řada představuje sadu datových bodů s jejich příslušnými kategoriemi a hodnotami. Přidáním více řad můžete porovnávat a analyzovat různé datové sady ve stejném sloupcovém grafu, což poskytuje komplexní pohled na vaše data.

#### Q3. Mohu přizpůsobit vzhled sloupcového grafu?
Ano, Aspose.Words for .NET vám umožňuje přizpůsobit různé aspekty vzhledu sloupcového grafu. Můžete upravit vlastnosti, jako je barva řady, popisky os, popisky dat a formátování oblasti grafu. Knihovna poskytuje bohatou sadu rozhraní API pro ovládání vizuálních prvků grafu a vytvoření přizpůsobeného vzhledu, který vyhovuje vašim potřebám.

#### Q4. Mohu uložit dokument s vloženým sloupcovým grafem v různých formátech?
 Ano, Aspose.Words for .NET umožňuje uložit dokument s vloženým sloupcovým grafem v různých formátech, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat požadovaný výstupní formát na základě vašich požadavků a použít`Save` metoda`Document` objekt pro uložení dokumentu. Vložený sloupcový graf zůstane v uloženém dokumentu zachován.

#### Q5. Mohu upravit data a vzhled sloupcového grafu po jeho vložení?
Ano, po vložení sloupcového grafu do dokumentu můžete upravit jeho data a vzhled pomocí API poskytovaných Aspose.Words for .NET. Data řady můžete aktualizovat novými kategoriemi a hodnotami, změnit barvy a formátování sloupců, přizpůsobit vlastnosti os a použít různé možnosti formátování k vytvoření dynamických a vizuálně přitažlivých grafů v dokumentech aplikace Word.