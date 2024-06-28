---
title: Vložit bublinový graf do dokumentu aplikace Word
linktitle: Vložit bublinový graf do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit bublinový graf do dokumentu pomocí Aspose.Words for .NET. Přidejte data série s hodnotami X, Y a velikosti bublin.
type: docs
weight: 10
url: /cs/net/programming-with-charts/insert-bubble-chart/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k vložení bublinového grafu do dokumentu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a uložit dokument.

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

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení bublinového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme tři datové body s odpovídajícími hodnotami X, Y a velikosti bublin.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Tím je implementace vkládání bublinového grafu pomocí Aspose.Words pro .NET dokončena.

### Příklad zdrojového kódu pro Vložit bublinový graf pomocí Aspose.Words pro .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak vložit bublinový graf do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit bublinový graf, přidat data sérií a uložit dokument s grafem.

Aspose.Words for .NET poskytuje výkonné rozhraní API pro textové zpracování s grafy v dokumentech aplikace Word. Bublinové grafy jsou ideální pro vizualizaci trojrozměrných dat, kde je každý datový bod reprezentován bublinou se souřadnicemi X a Y a hodnotou velikosti. S Aspose.Words for .NET můžete vytvářet dynamické a informativní bublinové grafy, které vylepšují vizuální reprezentaci vašich dat.

Pomocí Aspose.Words for .NET můžete automatizovat proces generování dokumentů s bublinovými grafy, což ušetří čas a námahu při ručním vytváření dokumentů. Knihovna nabízí širokou škálu typů grafů a možností přizpůsobení, což vám umožní vytvářet vizuálně přitažlivé grafy bohaté na data v dokumentech aplikace Word.

### Nejčastější dotazy

#### Q1. Co je bublinový graf?
Bublinový graf je typ grafu, který zobrazuje trojrozměrná data pomocí bublin nebo koulí. Každý datový bod je reprezentován bublinou, kde souřadnice X a Y určují polohu bubliny na grafu a velikost bubliny představuje třetí rozměr dat. Bublinové grafy jsou užitečné pro vizualizaci vztahů a vzorů mezi více proměnnými.

#### Q2. Mohu do bublinového grafu přidat více sérií?
Ano, pomocí Aspose.Words for .NET můžete do bublinového grafu přidat více řad. Každá řada představuje sadu datových bodů s příslušnými hodnotami X, Y a velikosti bublin. Přidáním více řad můžete porovnávat a analyzovat různé datové sady v rámci stejného grafu, což poskytuje komplexní pohled na vaše data.

#### Q3. Mohu přizpůsobit vzhled bublinového grafu?
Ano, pomocí Aspose.Words for .NET můžete přizpůsobit různé aspekty vzhledu bublinového grafu. Můžete upravit vlastnosti, jako je barva řady, velikost bublin, popisky os a formátování oblasti grafu. Knihovna poskytuje bohatou sadu rozhraní API pro ovládání vizuálních prvků grafu a vytvoření přizpůsobeného vzhledu, který vyhovuje vašim potřebám.

#### Q4. Mohu uložit dokument s vloženým bublinovým grafem v různých formátech?
 Ano, Aspose.Words for .NET umožňuje uložit dokument s vloženým bublinovým grafem v různých formátech, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat požadovaný výstupní formát na základě vašich požadavků a použít`Save` metoda`Document` objekt pro uložení dokumentu. Vložený bublinový graf zůstane v uloženém dokumentu zachován.

#### Q5. Mohu upravit data a vzhled bublinového grafu po jeho vložení?
Ano, po vložení bublinového grafu do dokumentu můžete upravit jeho data a vzhled pomocí API poskytovaných Aspose.Words pro .NET. Můžete aktualizovat data řady, změnit velikost bublin, přizpůsobit vlastnosti os a použít možnosti formátování k vytvoření dynamických a interaktivních grafů v dokumentech aplikace Word.