---
title: Vložit sloupcový graf do dokumentu aplikace Word
linktitle: Vložit sloupcový graf do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit sloupcový graf do dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/insert-column-chart/
---

Tento tutoriál vysvětluje, jak používat Aspose.Words pro .NET k vložení sloupcového grafu do dokumentu. Poskytnutý zdrojový kód ukazuje, jak vytvořit graf, přidat data řady a uložit dokument.

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

 Dále použijte`InsertChart` metoda`DocumentBuilder` pro vložení sloupcového grafu do dokumentu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 3: Přidejte do grafu data řady

Přidejte do grafu data řady. V tomto příkladu přidáme dvě kategorie a jejich odpovídající hodnoty.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Krok 4: Uložte dokument

 Nakonec uložte dokument do určeného adresáře pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Tím je implementace vkládání sloupcového grafu pomocí Aspose.Words pro .NET dokončena.

### Příklad zdrojového kódu pro vložení sloupcového grafu pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Závěr

tomto tutoriálu jste se naučili, jak vložit sloupcový graf do dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete vytvořit nový dokument, vložit sloupcový graf, přidat data řad a uložit dokument s grafem.

Aspose.Words for .NET poskytuje výkonné rozhraní API pro textové zpracování s grafy v dokumentech aplikace Word. Sloupcové grafy se běžně používají k zobrazení a porovnání dat v různých kategoriích nebo skupinách. S Aspose.Words for .NET můžete snadno vytvářet sloupcové grafy, které efektivně vizualizují vaše data a poskytují cenné informace.

Pomocí Aspose.Words for .NET můžete automatizovat proces generování dokumentů se sloupcovými grafy, čímž ušetříte čas a úsilí při ručním vytváření dokumentů. Knihovna nabízí širokou škálu typů grafů a možností přizpůsobení, což vám umožní vytvářet vizuálně přitažlivé grafy bohaté na data v dokumentech aplikace Word.

### Nejčastější dotazy

#### Q1. Co je sloupcový graf?
Sloupcový graf je typ grafu, který představuje data ve svislých sloupcích nebo sloupcích. Každý sloupec obvykle představuje kategorii nebo skupinu a výška nebo délka sloupce udává hodnotu dat spojených s danou kategorií. Sloupcové grafy se běžně používají k porovnání dat v různých kategoriích nebo ke sledování změn v průběhu času.

#### Q2. Mohu do sloupcového grafu přidat více řad?
Ano, pomocí Aspose.Words for .NET můžete do sloupcového grafu přidat více řad. Každá řada představuje sadu datových bodů s jejich příslušnými kategoriemi a hodnotami. Přidáním více řad můžete porovnávat a analyzovat různé datové sady v rámci stejného grafu, což poskytuje komplexní pohled na vaše data.

#### Q3. Mohu přizpůsobit vzhled sloupcového grafu?
Ano, pomocí Aspose.Words for .NET můžete přizpůsobit různé aspekty vzhledu sloupcového grafu. Můžete upravit vlastnosti, jako je barva řady, popisky os, šířka sloupce a formátování oblasti grafu. Knihovna poskytuje bohatou sadu rozhraní API pro ovládání vizuálních prvků grafu a vytvoření přizpůsobeného vzhledu, který vyhovuje vašim potřebám.

#### Q4. Mohu uložit dokument s vloženým sloupcovým grafem v různých formátech?
 Ano, Aspose.Words for .NET umožňuje uložit dokument s vloženým sloupcovým grafem v různých formátech, jako jsou DOCX, PDF, HTML a další. Můžete si vybrat požadovaný výstupní formát na základě vašich požadavků a použít`Save` metoda`Document` objekt pro uložení dokumentu. Vložený sloupcový graf zůstane v uloženém dokumentu zachován.

#### Q5. Mohu upravit data a vzhled sloupcového grafu po jeho vložení?
Ano, po vložení sloupcového grafu do dokumentu můžete upravit jeho data a vzhled pomocí API poskytovaných Aspose.Words for .NET. Můžete aktualizovat data řady, změnit barvy sloupců, přizpůsobit vlastnosti os a použít možnosti formátování k vytvoření dynamických a interaktivních grafů v dokumentech aplikace Word.