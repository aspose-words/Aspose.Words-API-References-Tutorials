---
title: Vložit bodový graf do dokumentu aplikace Word
linktitle: Vložit bodový graf do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit bodový graf do dokumentu pomocí Aspose.Words for .NET. Přidejte data série se souřadnicemi X a Y.
type: docs
weight: 10
url: /cs/net/programming-with-charts/insert-scatter-chart/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k vložení bodového grafu do dokumentu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a uložit dokument.

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

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení bodového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme dvě sady souřadnic X a Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Tím je implementace vkládání bodového grafu pomocí Aspose.Words pro .NET dokončena.

### Příklad zdrojového kódu pro Insert Scatter Chart pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Závěr

V tomto tutoriálu jste se naučili, jak vložit bodový graf do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit bodový graf, přidat data sérií se souřadnicemi X a Y a uložit dokument s grafem.

Aspose.Words for .NET poskytuje komplexní rozhraní API pro zpracování textu s grafy v dokumentech aplikace Word. Bodové grafy jsou užitečné pro vizualizaci a analýzu dat se dvěma číselnými proměnnými. S Aspose.Words for .NET můžete snadno vytvářet bodové grafy, které představují vztah mezi hodnotami X a Y a identifikují vzory nebo trendy v datech.

Pomocí Aspose.Words for .NET můžete automatizovat proces generování dokumentů s bodovými grafy, čímž ušetříte čas a úsilí při ručním vytváření dokumentů. Knihovna nabízí širokou škálu typů grafů, včetně bodových grafů, a poskytuje různé možnosti přizpůsobení pro přizpůsobení vzhledu grafu vašim potřebám.

### Nejčastější dotazy

#### Q1. Co je to bodový graf?
Bodový graf je typ grafu, který zobrazuje vztah mezi dvěma číselnými proměnnými. Skládá se ze série bodů vynesených na souřadnicové síti, přičemž jedna proměnná je znázorněna na ose X a druhá proměnná na ose Y. Bodové grafy se používají k identifikaci vzorů, korelací nebo trendů mezi dvěma sadami datových bodů.

#### Q2. Mohu do bodového grafu přidat více řad?
Ano, do bodového grafu můžete přidat více řad pomocí Aspose.Words for .NET. Každá řada představuje sadu datových bodů s jejich příslušnými souřadnicemi X a Y. Přidáním více řad můžete porovnávat a analyzovat různé datové sady v rámci stejného bodového grafu, což poskytuje komplexní pohled na vaše data.

#### Q3. Mohu přizpůsobit vzhled bodového grafu?
Ano, pomocí Aspose.Words for .NET můžete přizpůsobit různé aspekty vzhledu bodového grafu. Můžete upravit vlastnosti, jako je barva řady, tvar značky, popisky os a formátování oblasti grafu. Knihovna poskytuje bohatou sadu rozhraní API pro ovládání vizuálních prvků grafu a vytvoření přizpůsobeného vzhledu, který vyhovuje vašim potřebám.

#### Q4. Mohu uložit dokument s vloženým bodovým grafem v různých formátech?
Ano, Aspose.Words for .NET umožňuje uložit dokument s vloženým bodovým grafem v různých formátech, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat požadovaný výstupní formát na základě vašich požadavků a použít`Save` metoda`Document` objekt pro uložení dokumentu. Vložený bodový graf zůstane v uloženém dokumentu zachován.

#### Q5. Mohu upravit data a vzhled bodového grafu po jeho vložení?
Ano, po vložení bodového grafu do dokumentu můžete upravit jeho data a vzhled pomocí API poskytovaných Aspose.Words for .NET. Data série můžete aktualizovat pomocí nových souřadnic X a Y, změnit tvary a barvy značek, přizpůsobit vlastnosti os a použít možnosti formátování pro vytváření dynamických a interaktivních grafů v dokumentech aplikace Word.