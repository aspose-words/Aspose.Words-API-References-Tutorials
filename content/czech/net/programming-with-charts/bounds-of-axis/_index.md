---
title: Hranice Osy V Grafu
linktitle: Hranice Osy V Grafu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit hranice osy v grafu pomocí Aspose.Words for .NET ovládající rozsah hodnot zobrazených na ose.
type: docs
weight: 10
url: /cs/net/programming-with-charts/bounds-of-axis/
---

Tento tutoriál vysvětluje, jak nastavit hranice osy v grafu pomocí Aspose.Words for .NET. Vložením grafu, přidáním dat řady a konfigurací měřítka os můžete definovat minimální a maximální hodnoty pro osu.

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
 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder`objekt pracovat s dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložte a nakonfigurujte graf
 Vložte graf do dokumentu pomocí`InsertChart` metoda`DocumentBuilder` objekt. Nastavte požadovaný typ a rozměry grafu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Krok 4: Přidejte data série
Vymažte všechny existující řady v grafu a přidejte data nové řady. V tomto příkladu přidáme řadu s popisky "Položka 1" až "Položka 5" a odpovídajícími hodnotami.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Krok 5: Nastavte hranice osy
 Nakonfigurujte měřítko osy Y nastavením minimální a maximální hodnoty pomocí`Scaling.Minimum` a`Scaling.Maximum` vlastnosti osy.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Krok 6: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu uložíme dokument jako "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Příklad zdrojového kódu pro Bounds Of Axis pomocí Aspose.Words pro .NET 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

A je to! Úspěšně jste nastavili hranice osy v grafu pomocí Aspose.Words for .NET.

## Závěr
tomto tutoriálu jste se naučili, jak nastavit hranice osy v grafu pomocí Aspose.Words pro .NET. Podle podrobného průvodce můžete vložit a nakonfigurovat graf, přidat data řad a definovat minimální a maximální hodnoty pro měřítko os. Aspose.Words for .NET poskytuje výkonné a flexibilní rozhraní API pro zpracování textu s dokumenty aplikace Word, které vám umožňuje snadno vytvářet dynamické a vizuálně přitažlivé grafy.


### Nejčastější dotazy

#### Q1. Co je Aspose.Words for .NET?
Aspose.Words for .NET je knihovna, která umožňuje vývojářům pracovat s dokumenty Wordu programově. Poskytuje širokou škálu funkcí a funkcí pro vytváření, manipulaci a ukládání dokumentů aplikace Word.

#### Q2. Jak mohu nainstalovat Aspose.Words pro .NET?
Chcete-li nainstalovat Aspose.Words for .NET, můžete použít správce balíčků NuGet v sadě Visual Studio. Jednoduše vyhledejte „Aspose.Words“ ve správci balíčků NuGet a nainstalujte jej do svého projektu.

#### Q3. Mohu používat Aspose.Words pro .NET s jinými programovacími jazyky?
Ne, Aspose.Words for .NET je speciálně navržen pro aplikace .NET. Pracuje s programovacími jazyky jako C# a VB.NET.

#### Q4. Existují nějaké další předpoklady pro používání Aspose.Words pro .NET?
Kromě instalace knihovny Aspose.Words for .NET byste měli mít základní znalosti programování v C# a zpracování textu s dokumenty Word. Užitečná bude i znalost .NET frameworku.
