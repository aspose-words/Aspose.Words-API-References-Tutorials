---
title: Vytvořte a přizpůsobte graf pomocí tvaru
linktitle: Vytvořte a přizpůsobte graf pomocí tvaru
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit a přizpůsobit graf pomocí tvaru v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-charts/create-chart-using-shape/
---

Tento tutoriál vysvětluje, jak vytvořit graf pomocí tvaru v dokumentu aplikace Word pomocí Aspose.Words for .NET.

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
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Krok 4: Přizpůsobte graf
Přizpůsobte graf úpravou různých vlastností, jako je název grafu a legenda.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Krok 5: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithCharts.CreateChartUsingShape.docx“.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Příklad zdrojového kódu pro Create Chart Using Shape using Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Upozorňujeme, že pokud je jako text nadpisu zadána hodnota null nebo prázdná, zobrazí se automaticky generovaný název.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

A je to! Úspěšně jste vytvořili graf pomocí tvaru v dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Závěr
tomto tutoriálu jste se naučili, jak vytvořit graf pomocí tvaru v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce můžete vložit a nakonfigurovat tvar grafu, přizpůsobit jeho vzhled a uložit dokument. Aspose.Words for .NET poskytuje komplexní sadu funkcí pro zpracování textu s dokumenty a grafy aplikace Word, což vám umožňuje vytvářet profesionálně vypadající a vizuálně přitažlivé grafy přímo ve vašich aplikacích .NET.

### Nejčastější dotazy

#### Q1. Mohu vytvořit grafy v dokumentu aplikace Word pomocí Aspose.Words for .NET?
Ano, pomocí Aspose.Words for .NET můžete programově vytvářet grafy v dokumentu aplikace Word. Aspose.Words poskytuje API a funkce pro vkládání různých typů grafů, přizpůsobení jejich vzhledu a manipulaci s daty grafů.

#### Q2. Jaké typy grafů podporuje Aspose.Words pro .NET?
Aspose.Words for .NET podporuje širokou škálu typů grafů, včetně spojnicových grafů, sloupcových grafů, koláčových grafů, plošných grafů, bodových grafů a dalších. Můžete si vybrat vhodný typ grafu na základě vašich dat a požadavků na vizualizaci.

#### Q3. Mohu upravit vzhled vytvořeného grafu?
Ano, vzhled vytvořeného grafu můžete upravit pomocí Aspose.Words for .NET. Vlastnosti, jako je název grafu, pozice legendy, popisky dat, popisky os, barvy a další vizuální prvky, můžete upravit tak, aby vyhovovaly vašim specifickým potřebám návrhu a formátování.
